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
##### One user sends requests one after another for 10 seconds
Add:
```
export const options = {
	vus: 1,
	duration: '10s'
}
```
##### 1000 users send continuous requests for 60 seconds
Add:
```
export const options = {
	vus: 1000,
	duration: '60s'
}
```

##### Load Test
Testing how your application will behave under the average load your application receives.

Test in multiple stages. Example - ramp upto 20 users for 20 seconds and then ramp down to 0 for the next 10.
```
export const options = {
	stages: [
		{ duration: '20s', target: 20 },
		{ duration: '10s', target: 0 },
	]
}
```
