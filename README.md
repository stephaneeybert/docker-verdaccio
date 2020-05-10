The local npm registry

https://verdaccio.org


Some commands

Check that the host port is open
nmap -p 4873 localhost

Access the registry
http://verdaccio:4873

The packages are installed under the directory storage/data


Stopping the registry

On the remote

```
docker stack rm verdaccio-registry
```
