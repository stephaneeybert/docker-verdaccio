Installation

On the local

Create the project directory
```
mkdir -p ~/dev/docker/registries/verdaccio
```

Create the volume directory
```
mkdir -p ~/dev/docker/registries/verdaccio/volumes/conf;
mkdir -p ~/dev/docker/registries/verdaccio/volumes/plugins;
mkdir -p ~/dev/docker/registries/verdaccio/volumes/storage;
```

Create the configuration and the password file
```
vi ~/dev/docker/registries/verdaccio/volumes/conf/config.yaml
touch ~/dev/docker/registries/verdaccio/volumes/conf/htpassword
```

Allow large archives
In the volumes/conf/config.yaml configuration file have the property:
```
max_body_size: 1000mb
```

Add the hostname in the /etc/hosts file
```
127.0.1.1 verdaccio
```

Store packages with the scope stephane in verdaccio:4873 even if the current registry is registry.npmjs.org
```
npm config set @stephaneeybert:registry http://verdaccio:4873
```

Start the registry
```
cd ~/dev/docker/registries/verdaccio/;
docker stack deploy --compose-file docker-compose.yml verdaccio-registry
```

Log in the registry
```
npm login --registry http://verdaccio:4873
Login: stephane
Password: m...
```

Stopping the registry
```
docker stack rm verdaccio-registry
```

