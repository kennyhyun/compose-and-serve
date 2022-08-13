# compose-and-serve
docker compose samples for a various services

## Traefik

Traefik is a load balancer and `traefik` directory has the container settings

Traefik container is using acme protocol to create let's encrypt certificates automatically.

You will need to set the email and the domain to create the certificates.

the configuration will set traefik.domain-you-set and bt.domain-you-set

#### Configuration

- Copy `.env.sample` to `.env` and edit your domain and email address in it.
- Run the command to set the `data/user.secrets`
  - `htpasswd -nB <user> | tee data/user.secrets` -- modify `<user>` as your login user to the traefik dashboard

** To install htpasswd, run `sudo apt install apache2-utils` for Ubuntu for example

#### Running the container

- `chmod 600 data/acme.json`
- `docker-compse up -d` or `docker compse up -d` in the `traefik` directory.

you will see the traefik dashbaord in `http://192.168.0.2:8080` where your server address is `192.168.0.2` and
`https://traefik.<domain-you-set>/`


#### If the certificates not generated

- check the permission of the `data/acme.json`. it should be 600
- open both 80 and 443 ports for the inbound connection for the server
