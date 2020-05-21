Installation

On the local

Create the project directory
```
mkdir -p ~/dev/docker/registries/verdaccio
```

Create the volume directory
```
mkdir -p ~/dev/docker/registries/verdaccio/volumes/conf
mkdir -p ~/dev/docker/registries/verdaccio/volumes/plugins
mkdir -p ~/dev/docker/registries/verdaccio/volumes/storage
```

Create the configuration and the password file
```
vi ~/dev/docker/registries/verdaccio/volumes/conf/config.yaml
touch ~/dev/docker/registries/verdaccio/volumes/conf/htpassword
```

Add the hostname in the /etc/hosts file
```
127.0.1.1 verdaccio
```

Copy the a file
```
scp ~/dev/docker/registries/verdaccio/docker-compose.yml stephane@149.28.60.185:~/dev/docker/registries/verdaccio/
```

On the remote

Make sure the firewall leaves open the registry port

Create the directory
```
mkdir -p ~/dev/docker/registries/verdaccio
```

Create the volume directory
```
mkdir -p ~/dev/docker/registries/verdaccio/storage
```

Start the registry
```
cd ~/dev/docker/registries/verdaccio/;
docker stack deploy --compose-file docker-compose.yml verdaccio-registry
```

