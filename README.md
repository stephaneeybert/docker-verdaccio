The local npm registry

https://verdaccio.org


Some commands

Check that the host port is open
nmap -p 4873 localhost

Access the registry
http://verdaccio:4873

The packages are installed under the directory ~/dev/docker/storage/data


Stopping the registry
```
docker stack rm verdaccio-registry
```
