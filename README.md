# docker-compose-watchtower

A docker compose file for my watchtower environment.

## Usage 

### Configure

To schedule watchtower to run at a specific time change the `WATCHTOWER_SCHEDULE` environment value to the time you want the checks to run.  This uses 6 fields and more details can be found [here](https://pkg.go.dev/github.com/robfig/cron@v1.2.0#hdr-CRON_Expression_Format).

```
Seconds       (0-59)
Minute        (0-59)
Hours         (0-23) 
Day of month  (1-31)
Month         (1-12)
Day of week   (0-6, 6=Sunday)
```

To configure the timezone used change the `TZ` environment value to the correct timezone.  A list of valid timezones can be found [here](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List).

### Starting

```bash
cd ~/watchtower       # change to the watchtower directory
docker compose pull   # pulls the latest image
docker compose up -d  # starts container in detached mode

```

### Stopping

```bash
cd ~/watchtower      # change to the watchtower directory
docker compose down  # stops the container
```

### Updating

```bash
cd ~/watchtower         # change to the watchtower directory
docker compose pull     # pulls the latest image
docker compose up -d    # restarts the containers with the newer images
docker system prune -a  # deletes any unused images
```

### Uninstall

```bash
cd ~/watchtower         # change to the watchtower directory
docker compose down -v  # stops the container and deletes the data volumes
docker system prune -a  # deletes any unused container images
```

## License

MIT

## Author Information

This project was created in 2022 by Graham Lillico.
