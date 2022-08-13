# compose-and-serve
docker compose samples for a various services

## Traefik

Traefik is a load balancer and `traefik` directory has the container settings

Traefik container is using acme protocol to create let's encrypt certificates automatically.

You will need to set the email and the domain to create the certificates.

the configuration will set traefik.domain-you-set and bt.domain-you-set

#### Configuration



- Copy `traefik/.env.sample` to `traefik.env` and set your domain and email address.
- Run the command to set the `traefik/data/user.secrets`
  -   

#### Running the container

`docker-compse up -d` in the `traefik` directory.

you will see the traefik dashbaord in `http://192.168.0.2:8080` where your server address is `192.168.0.2` and
`https://traefik.<domain-you-set>/`


