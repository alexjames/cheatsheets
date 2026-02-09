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
docker container kill <container_id>
```

Run bash in an image
```
docker run --rm -it --entrypoint bash <image name>
```

Copy a file out of a docker container
```
docker cp <container id>:<file_path> .
```
