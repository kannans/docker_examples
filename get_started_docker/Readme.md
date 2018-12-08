Build a image

```
 docker build -t friendlyhello .
```

run the image

```
docker run -p 4000:80 friendlyhello
```

Run the app in background mode

```
docker run -d -p 4000:80 friendlyhello
```

Stop the container

```
docker container stop 1fa4ab2cf395

```