# neosvr-headless
Docker image of a NeosVR headless server based on shadowpanther/neosvr-headless

## Requirements
* Docker
* Steam Account with SteamGuard disabled (You might want a separate Steam account for running the headless server)

## Preparation
1. Sign up for NeosVR Patron, level "Guntry" or higher for headless access
2. Get Beta key from Discord
3. Copy `.env.sample` to `.env` and add your Steam Credentials and Beta Password found in the last step
4. Update `Config/Config.json` with the NeosVR config you would like to start with.

## Build the image
```bash
# If you have Make installed, simply run
make build

# If you do not have Make installed, run:
docker compose build
```

## Run NeosVR Headless
```bash
# If you have Make installed, simply run
make up

# If you do not have Make installed, run:
docker compose up -d
```

## Stop NeosVR
```bash
# If you have Make installed, simply run
make down

# If you do not have Make installed, run:
docker compose down
```

You probably need to set `vm.max_map_count=262144` by doing `echo "vm.max_map_count=262144" >> /etc/sysctl.conf` lest you end up with frequent GC crashes.
