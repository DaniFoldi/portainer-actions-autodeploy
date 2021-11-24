# Portainer Actions Autodeploy

## Checklist
- [ ] Select and change `LICENSE`
- [ ] Verify `Dockerfile`
- Secrets
  - [ ] PORTAINER_HOST (hostname of portainer)
  - [ ] PORTAINER_USER (user to use for deployment, admin not recommended)
  - [ ] PORTAINER_KEY (password of user)
  - [ ] PORTAINER_ENDPOINT (endpoint id of portainer environment)
- Replace these values in all files
  - `<CONTAINER_NAME>` usually owner/repository
  - `<STACK_NAME>` for example gh-repository
  - `<SERVICE>` traefik and docker service name
  - `<DOMAIN>` traefik host
  - `<NETWORK_NAME>` docker network to attach
```bash
sed -i'.old' 's/<NETWORK_NAME>/docker-data_traefik-proxy/' docker-compose.yml .github/workflows/*.yml
sed -i'.old' 's/<CONTAINER_NAME>/DaniFoldi\//g' docker-compose.yml .github/workflows/*.yml
sed -i'.old' 's/<SERVICE>//g' docker-compose.yml .github/workflows/*.yml
sed -i'.old' 's/<DOMAIN>//g' docker-compose.yml .github/workflows/*.yml
grep -n "<.*>" *.yml .github/workflows/*.yml
```
