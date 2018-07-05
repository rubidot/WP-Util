# WP Util

## Start Container

### SFTP Credentials
For SFTP utilities, a `sftp-config` file must be mounted at root with format:

```
HOSTNAME=
USERNAME=
PASSWORD='password'
PORT=
```

### Set Varibales
```shell
CONTAINERNAME=wputil
BACKUPS= # backups volume
WP= # wordpress install volume
NETWORK= # wordpress container network
```
To specify directories relative to your current working directory,
you can use:
```shell
`pwd`/rest/of/path
```

### Start Container
```shell
docker run -it --rm \
--name $CONTAINERNAME \
-v "$BACKUPS:/backups" \
-v "$WP:/var/www/html" \
--network=$NETWORK \
rubidot/wputil
```

## Detach
`CTRL+p` `CTRL+q`

## Re-attach
```shell
docker attach $CONTAINERNAME
```

## Exit
`exit`
