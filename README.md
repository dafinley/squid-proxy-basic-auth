
# Basic Authentication Squid Docker

Minimal docker image with [Squid] that only proxies authenticated requests and (optionally) only to certain domains.

### Usage

Build the Docker Image

```
docker build -t squid-auth:1.0 .
```

Create the new container from the squid-auth:1.0 image

```
docker run -d -e PROXY_USERNAME=doug.finley -e PROXY_PASSWORD=password -p 3128:3128 squid-auth:1.0
```

When accessing the proxy, proxy user will be ```PROXY_USERNAME```, and password will be whatever you set in ```PROXY_PASSWORD```

For Example

```
curl --proxy-basic --proxy-user doug.finley:password --proxy http://127.0.0.1:3128 http://www.google.com
```

License
----

BSD

   [squid]: <http://www.squid-cache.org/>
