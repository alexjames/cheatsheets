##### Container management
Run Jetty webserver
```
docker run -p 80:8080 jetty
```

Run Jetty as a service
```
docker run -d -p 80:8080 jetty
```

Check what containers are currently running
```
docker container ls
```

Kill running container
```
docker container kill <container id>
```
