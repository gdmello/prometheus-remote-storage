Introduction
============
A small repo to verify prometheus v1.x LTS (Long Term Storage).

Useage
======

docker run -v `pwd`:/tmp/prometheus -p 9090:9090 prom/prometheus --config.file "/tmp/prometheus/prometheus.yml"
docker run -p 8086:8086 -v $PWD:/var/lib/influxdb influxdb
./remote_storage_adapter -influxdb-url http://localhost:8086
./node_exporter


Deploy [prometheus-operator](https://github.com/coreos/prometheus-operator) -

    $ kubectl create -f prometheus-operator.yaml


Once the TPR, prometheus is registered, with the above step, deploy the prometheus pod and a service to expose it to the UI -

    $ kubectl create -f prometheus-k8s.yaml