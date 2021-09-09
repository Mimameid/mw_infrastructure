### HOWTO

1. Install docker

2. Install docker compose

3. On your host that will run elasticsearch, run: `sysctl -w vm.max_map_count=262144`

   To make it persistent, add the following line to `/etc/sysctl.conf`:

   `vm.max_map_count=262144`

   and run

   `sudo sysctl -p`

4. For Dev run:
   `docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d`
5. For Prod run:
   `docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d`
