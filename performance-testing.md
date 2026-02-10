Performance testing using `k6`.
##### Send single request 
Write this function in `test.js`:
```
import http from 'k6/http';

export default () => {
	http.get('http://ec2-34-211-23-81.us-west-2.compute.amazonaws.com')
}
```
Run: 
```
k6 run test.js
```
