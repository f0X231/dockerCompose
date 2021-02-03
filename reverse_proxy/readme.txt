# ref : https://medium.com/@peerapats/host-%E0%B8%AB%E0%B8%A5%E0%B8%B2%E0%B8%A2-websites%E0%B9%83%E0%B8%99%E0%B9%80%E0%B8%84%E0%B8%A3%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%87%E0%B9%80%E0%B8%94%E0%B8%B5%E0%B8%A2%E0%B8%A7-%E0%B8%94%E0%B9%89%E0%B8%A7%E0%B8%A2-docker-nginx-b5002660f196

# Step
1. docker network create sandbox_network
2. docker run -d \
  --name reverse-proxy \
  -p 80:80 \
  -v /var/run/docker.sock:/tmp/docker.sock:ro \
  --net sandbox_network jwilder/nginx-proxy


