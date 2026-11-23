### POSTGRES container setup
Run container
```
docker run --name my-postgre \
  -e POSTGRES_PASSWORD=mysecretpassword \
  -p 5432:5432 \
  postgres:latest
```

Restart container
```
docker start my-postgre
```

Start psql
```
docker exec -it my-postgre psql -U postgres
```

### Looking around
List databases
```
\l
```

List tables
```
\dt
```

Get connection info
```
\conninfo
```

Connect to a database
```
\c <db_name>
```


### Data creation
Create database
```
postgres=# create database <db_name>;
CREATE DATABASE
```

Connect to database
```
\c <db_name>
```

Create Items table
```
CREATE TABLE items (
    id BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    sku VARCHAR(64) UNIQUE NOT NULL,
    name VARCHAR(255) NOT NULL,
    description TEXT,
    price_cents INTEGER NOT NULL CHECK (price_cents >= 0),
    quantity INTEGER NOT NULL DEFAULT 0 CHECK (quantity >= 0),
    is_active BOOLEAN NOT NULL DEFAULT TRUE,
    created_at TIMESTAMPTZ NOT NULL DEFAULT NOW(),
    updated_at TIMESTAMPTZ NOT NULL DEFAULT NOW()
);

CREATE TABLE orders (
    id BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    user_id BIGINT NOT NULL,
    status VARCHAR(32) NOT NULL DEFAULT 'pending'
        CHECK (status IN ('pending', 'paid', 'shipped', 'delivered', 'cancelled', 'refunded')),
    total_cents INTEGER NOT NULL CHECK (total_cents >= 0),
    currency CHAR(3) NOT NULL DEFAULT 'USD',
    shipping_address JSONB,
    created_at TIMESTAMPTZ NOT NULL DEFAULT NOW(),
    updated_at TIMESTAMPTZ NOT NULL DEFAULT NOW()
);

CREATE TABLE order_items (
    id BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    order_id BIGINT NOT NULL REFERENCES orders(id) ON DELETE CASCADE,
    item_id BIGINT NOT NULL REFERENCES items(id) ON DELETE RESTRICT,
    quantity INTEGER NOT NULL CHECK (quantity > 0),
    unit_price_cents INTEGER NOT NULL CHECK (unit_price_cents >= 0),
    UNIQUE (order_id, item_id)
);
```

Insert some sample data
```
-- 1. Reset tables and restart identity counters at 1
TRUNCATE TABLE order_items, orders, items RESTART IDENTITY;

-- 2. Insert items
INSERT INTO items (sku, name, description, price_cents, quantity, is_active)
VALUES
    ('TSHIRT-BLK-M', 'Classic Cotton Tee (M)', '100% organic cotton crewneck t-shirt in black', 2500, 120, TRUE),
    ('HAT-NVY-OS', 'Canvas Dad Cap', 'Adjustable navy brushed canvas cap', 1800, 45, TRUE),
    ('MUG-CER-12', 'Matte Ceramic Mug (12oz)', 'Dishwasher-safe speckled stoneware mug', 1650, 80, TRUE),
    ('BACKPACK-GRY', 'Commuter Laptop Backpack', 'Water-resistant 20L pack with padded 16-inch sleeve', 8900, 15, TRUE),
    ('SOCKS-WHT-3PK', 'Cushioned Crew Socks (3-Pack)', 'Breathable athletic crew socks', 1400, 0, TRUE),
    ('JACKET-OLV-L', 'Waxed Utility Jacket (L)', 'Seasonal heavyweight canvas jacket (discontinued)', 14500, 0, FALSE);

-- 3. Insert orders
INSERT INTO orders (user_id, status, total_cents, currency, shipping_address, created_at)
VALUES
    (1001, 'delivered', 12900, 'USD', '{"street": "742 Evergreen Terrace", "city": "Springfield", "state": "OR", "zip": "97477"}'::jsonb, NOW() - INTERVAL '14 days'),
    (1002, 'shipped', 3300, 'USD', '{"street": "1600 Amphitheatre Pkwy", "city": "Mountain View", "state": "CA", "zip": "94043"}'::jsonb, NOW() - INTERVAL '3 days'),
    (1001, 'paid', 6100, 'USD', '{"street": "742 Evergreen Terrace", "city": "Springfield", "state": "OR", "zip": "97477"}'::jsonb, NOW() - INTERVAL '6 hours'),
    (1003, 'pending', 14500, 'USD', '{"street": "350 Fifth Ave", "city": "New York", "state": "NY", "zip": "10118"}'::jsonb, NOW() - INTERVAL '15 minutes'),
    (1004, 'cancelled', 1800, 'USD', '{"street": "221B Baker St", "city": "London", "country": "UK", "zip": "NW1 6XE"}'::jsonb, NOW() - INTERVAL '5 days');

-- 4. Insert order_items safely using SKU lookups instead of hardcoded item IDs
INSERT INTO order_items (order_id, item_id, quantity, unit_price_cents)
SELECT v.order_id, i.id, v.quantity, v.unit_price_cents
FROM (VALUES
    (1, 'TSHIRT-BLK-M', 2, 2500),
    (1, 'BACKPACK-GRY', 1, 7900),
    (2, 'MUG-CER-12',   2, 1650),
    (3, 'TSHIRT-BLK-M', 1, 2500),
    (3, 'HAT-NVY-OS',   2, 1800),
    (4, 'JACKET-OLV-L', 1, 14500),
    (5, 'HAT-NVY-OS',   1, 1800)
) AS v(order_id, sku, quantity, unit_price_cents)
JOIN items i ON i.sku = v.sku;
```
