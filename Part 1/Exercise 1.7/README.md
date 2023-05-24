# Dockerfile

```
FROM ubuntu:20.04
WORKDIR /usr/src
RUN apt-get update
RUN apt-get -y install curl
COPY search.sh .
RUN chmod +x search.sh
CMD ./search.sh
```

# Output

![Output](Screenshot.png)
