# Docker registry server

## Generate certificates

```
openssl req  -newkey rsa:4096 -nodes -sha256 \
    -keyout certs/domain.key -x509 -days 365 -out certs/domain.crt
```

## Create a password file

```
docker run \
  --entrypoint htpasswd \
  registry:2 -Bbn testuser testpassword > auth/htpasswd
```