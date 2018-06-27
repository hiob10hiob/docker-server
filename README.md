# Dockerized vServer with Traefik, Gitlab and a Webserver

My vServer setup to run Gitlab and a simple Webserver.
Using [docker-compose] (https://docs.docker.com/compose/) for easy deployment. The folowing offical containers are used:
 - [traefik] (https://hub.docker.com/r/library/traefik/)
 - [nginx] (https://hub.docker.com/_/nginx/)
 - [gitlab-ce] (https://hub.docker.com/r/gitlab/gitlab-ce/)

## Requirments
  - [docker](https://www.docker.com/) [Install Doc] (https://docs.docker.com/install/linux/docker-ce/debian/#os-requirements)
  - [docker-compose](https://docs.docker.com/compose/)
  - `apache2-utils`
  - Domain with subdomains (www, git, monitor) pointing to your vServers public ip adress.

## Deployment
  1.  Clone Repo
  2. Generate password wirh `htpasswd`
      ```
      htpasswd -nb admin secure_password
      ```
  3. Edit `traefik.toml`
  4. Edit all `docker-compose.yml`
  5. use `docker-compose up -d` to start traefik
  6. Edit `/gitlab/docker-compose.yml`
  7. Move into subdirectories and start services with `docker-compose up -d`

## Where is my data stored?

 You can find your files hier:
 - Gitlab
    - `/gitlab/config`
    - `/gitlab/logs`
    - `/gitlab/data`
 - Webserver
    - `/webserver/html
  `  



## Links

- https://stackoverflow.com/questions/48408184/traefik-will-issue-certificate-instead-of-lets-encrypt
- https://docs.traefik.io/configuration/acme/#onhostrule
- https://docs.traefik.io/configuration/acme/
- https://www.digitalocean.com/community/tutorials/how-to-use-traefik-as-a-reverse-proxy-for-docker-containers-on-ubuntu-16-04
:
- https://www.reddit.com/r/docker/comments/8mwuf8/gitlab_wont_work_with_traefik/
