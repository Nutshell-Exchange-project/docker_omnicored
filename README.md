# mpugach/omnicored

An [omnicore](https://github.com/OmniLayer/omnicore) docker image.

## Tags

- `v0.8.2-alpine`, `latest` ([v0.7.0-alpine/Dockerfile](https://github.com/Nutshell-Exchange-project/docker_omnicored/blob/master/v0.8.2-alpine/Dockerfile))


## Examples

`docker-compose` example:

```yml
version: '3'

services:
  omnicored:
    image: mpugach/omnicored
    volumes:
      - omnicore:/home/bitcoin/.bitcoin
    ports:
      - "18332:18332"
    command: "-server -regtest -txindex -rpcuser=username -rpcpassword=password -rpcallowip=172.0.0.0/8 -printtoconsole"

volumes:
  omnicore:
```

command-line example:

```sh
docker run --rm --name omnicore-server -it mpugach/omnicored \
  -server -regtest -txindex -rpcuser=username \
  -rpcpassword=password -rpcallowip=172.0.0.0/8 \
  -printtoconsole
```

for v0.7.0

`docker-compose` example:

```yml
version: '3'

services:
  omnicored:
    image: mpugach/omnicored
    volumes:
      - omnicore:/home/bitcoin/.bitcoin
    ports:
      - "127.0.0.1:18332:18332"
    command: "-server -regtest -txindex -rpcuser=username -rpcpassword=password -rpcallowip=172.0.0.0/8 -printtoconsole -rpcbind=0.0.0.0:18332"

volumes:
  omnicore:
```

command-line example:

```sh
docker run --rm --name omnicore-server -it mpugach/omnicored \
  -server -regtest -txindex -rpcuser=username \
  -rpcpassword=password -rpcallowip=172.0.0.0/8 \
  -printtoconsole  -rpcbind=0.0.0.0:18332
```
