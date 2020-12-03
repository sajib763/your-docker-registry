# Local docker registry

### Step 1: Prerequisits

  - Install [docker](https://docs.docker.com/get-docker/)  
  - Install [docker compose](https://docs.docker.com/compose/install/)

### Step 2: Checkout this repository

  - Open the **docker-compose.yml** file
  - Configure the **containers name** and **ports** accordingly

### Step 3: Add insecure registry lists

By default docker uses secured HTTP or HTTPS. Since we are running this registry locally so there can be exceptions to tell docker about it. So open the file **/etc/docker/daemon.json** (if not exists then create it please!) and add the following json:

```sh
    {
        "insecure-registries" : ["your.resgisty.host.ip:port"]
    }
```

Now restart the docker service

```sh
    service docker restart
```

### Step 4: Run it !
Hit the following command and your local registry is up for service:
```sh
    docker-compose up -d
```
### Step 5: Browse your registry
According to the given example in the **docker-compose.yml** file the docker registry container UI has binded with the host port 25001, so the URL should be:
```sh
    http://host-ip:25001
```

**Special thanks to [konradkleine](https://hub.docker.com/r/konradkleine/docker-registry-frontend/) for the registry UI image :)**
