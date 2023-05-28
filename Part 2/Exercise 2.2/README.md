# Docker compose yml

```yml
version: "3.8"
services:
  simple-web-service:
    image: devopsdockeruh/simple-web-service
    build: .
    container_name: simple-web-service
    ports:
      - 3000:8080
    command: "server"
```
