# docker-influxdb
InfluxDB - Component of the TICK Stack

see: https://hub.docker.com/_/influxdb/

see: https://github.com/influxdata/TICK-docker

Get default InfluxDB config
```bash
docker run --rm influxdb:${IMAGE_TAG:-1.7.0} influxd config > influxdb.conf
```

Create influxdb database
```bash
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=CREATE DATABASE cadvisor"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=CREATE USER cadvisor WITH PASSWORD 'cadvisor'"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=GRANT ALL PRIVILEGES ON cadvisor TO cadvisor"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=GRANT WRITE ON cadvisor TO cadvisor"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=GRANT READ ON cadvisor TO cadvisor"
```

Create telegraf database
```bash
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=CREATE DATABASE telegraf"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=CREATE USER telegraf WITH PASSWORD 'telegraf'"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=GRANT ALL PRIVILEGES ON telegraf TO telegraf"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=GRANT WRITE ON telegraf TO telegraf"
curl -i -XPOST "http://${INFLUXDB_HOST_PORT:-localhost:8086}/query" --data-urlencode "q=GRANT READ ON telegraf TO telegraf"
```
