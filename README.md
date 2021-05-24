# Private Docker Registry

```
	git clone https://github.com/rjsocha/docker-registry.git
	cd docker-registry
	cp .env.sample .env
	# setup hostname & secret in .env file
	docker-compose up -d
```

requires [docker-traefik-gateway](https://github.com/rjsocha/docker-traefik-gateway) to be up & running.

For pull (read only) access use:
```
login: pull
pass: pull
```

For push (read&write) access use:
```
login: push
pass: push
```

change passwords/add new user(s):

```
docker run --rm -v $(pwd)/auth/passwd:/passwd httpd:alpine htpasswd -B /passwd pull
docker run --rm -v $(pwd)/auth/passwd:/passwd httpd:alpine htpasswd -B /passwd push
docker run --rm -v $(pwd)/auth/passwd:/passwd httpd:alpine htpasswd -B /passwd newuser
```
