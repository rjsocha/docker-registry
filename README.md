# Docker registry

```
	git clone https://github.com/rjsocha/docker-registry.git
	cd docker-registry
	cp .env.sample .env
	# setup hostname & secret in .env file
	docker-compose up -d
```

requires [docker-traefik-gateway](https://github.com/rjsocha/docker-traefik-gateway) to be up & running.
