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
CONTAINER ID        IMAGE                                          COMMAND                  CREATED             STATUS              PORTS               NAMES
41c4f9449f8c        prom/prometheus:v1.7.1                         "/bin/prometheus --co"   17 minutes ago      Up 15 minutes                           prometheusremotestorage_prometheus_1
af7f830a2026        gavind/prometheus-remote-storage-adapter:1.0   "./remote_storage_ada"   17 minutes ago      Up 15 minutes                           prometheusremotestorage_remotestorageadapter_1
31eb292c3b36        influxdb                                       "/entrypoint.sh influ"   20 minutes ago      Up 15 minutes                           prometheusremotestorage_influxdb_1
3ada1094868e        quay.io/prometheus/node-exporter               "/bin/node_exporter -"   20 minutes ago      Up 15 minutes                           prometheusremotestorage_nodeexporter_1
```

Build
=====
Build the Prometheus remote storage adapter with-
```
$ cd remote_storage_adapter
$ docker build .
Sending build context to Docker daemon 44.91 MB
Step 1 : FROM ubuntu:14.04
 ---> c69811d4e993
Step 2 : COPY remote_storage_adapter /
 ---> 6973e5346f20
Removing intermediate container 8383e6d8aa68
Step 3 : RUN chmod 755 /remote_storage_adapter
 ---> Running in 9d0bca58596e
 ---> 1adb1e1580d1
Removing intermediate container 9d0bca58596e
Step 4 : ENTRYPOINT ./remote_storage_adapter
 ---> Running in 4f68bdb5b5d7
 ---> 96fc991f2cfa
Removing intermediate container 4f68bdb5b5d7
Successfully built 96fc991f2cfa

$ docker tag 96f gdmello/prometheus-remote-storage-adapter:1.0
```