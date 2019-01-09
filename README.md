# Next.js with Docker, PM2 and NGINX

This project is a production Docker setup for a Next.js app.

The Next.js app is launched with [PM2 Runtime](https://pm2.io/runtime/), which is a Production Process Manager for Node.js applications and is used to keep the app alive forever.

A second container with the [NGINX](https://www.nginx.com/) web server is used as a reverse proxy, and to handle HTTP caching.

## Docker

```
docker-compose up
```

NGINX listens on port 80, which is the default HTTP port, so you can just visit **http://localhost/**

## PM2 commands

PM2 commands can still be used inside a container with the `docker exec` command:

```
docker exec -it <container-id> pm2 monit          # Monitoring CPU/Usage of each process
```
```
docker exec -it <container-id> pm2 list           # Listing managed processes
```
```
docker exec -it <container-id> pm2 show           # Get more information about a process
```
```
docker exec -it <container-id> pm2 reload all     # 0sec downtime reload all applications
```
