# Portainer Actions Autodeploy

## Checklist
- [ ] Select and change `LICENSE`
- [ ] Verify `Dockerfile`
- Secrets
  - [ ] GITHUB_TOKEN (package read/write)
  - [ ] PORTAINER_HOST (hostname of portainer)
  - [ ] PORTAINER_USER (user to use for deployment, admin not recommended)
  - [ ] PORTAINER_KEY (password of user)
  - [ ] PORTAINER_ENDPOINT (endpoint id of portainer environment)
- Replace these values in all files `grep "<.*>" *`
  - `<CONTAINER_NAME>` usually owner/repository
  - `<STACK_NAME>` for example gh-repository
  - `<SERVICE>` traefik and docker service name
  - `<DOMAIN>` traefik host
  - `<NETWORK_NAME>` docker network to attach
