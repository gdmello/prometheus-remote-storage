Introduction
============
A small repo to verify prometheus v1.x LTS (Long Term Storage).

Usage
======
* Start Prometheus, InfluxDB, node_exporter and Prometheus remote storage adapter-
```
$ docker-compose up
```
This should now bring up these docker containers-
```
$ docker ps
CONTAINER ID        IMAGE                                          COMMAND                  CREATED             STATUS              PORTS                    NAMES
488f61b2bfc4        gavind/prometheus-remote-storage-adapter:0.1   "./remote_storage_ada"   2 minutes ago       Up 2 seconds                                 prometheusremotestorage_remotestorageadapter_1
69e305b23204        quay.io/prometheus/node-exporter               "/bin/node_exporter -"   About an hour ago   Up 2 seconds        0.0.0.0:9100->9100/tcp   prometheusremotestorage_nodeexporter_1
08c78552283c        prom/prometheus                                "/bin/prometheus --co"   About an hour ago   Up 2 seconds        0.0.0.0:9090->9090/tcp   prometheusremotestorage_prometheus_1
2dcc2d3eedb6        influxdb                                       "/entrypoint.sh influ"   About an hour ago   Up 2 seconds        0.0.0.0:8086->8086/tcp   prometheusremotestorage_influxdb_1
```