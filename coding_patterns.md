### Pagination
```
BAD - function call repeated twice

resp = client.GetResource(input)
next_token = resp.next_token
while next_token != nil {
  resp = client.GetResource(input, next_token)
  next_token = resp.next_token
}


GOOD:
next_token = nil
for {
  resp = client.GetResource(input, next_token)
  if resp.next_token == nil {
    break
  }
  next_token = resp.next_token
}
```
