

Create docker image
```
docker build . -t httpserver
```

Start a docker swarm
```
docker swarm init
```

Create a stack
```
docker deploy --compose-file stack.yml httpstack
```

Scale to a specific number for replica
```
docker service scale httpstack_httpserver=2
```

And you will see your high available service
```
# curl 127.0.0.1
This is container: 29f2bf28c385
# curl 127.0.0.1
This is container: e4366a42d981
```

Clean up:
```
docker swarm leave --force
```
