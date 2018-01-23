
# Docker => Journald => fluent-bit => Elasticsearch flow example

1. Run Vagrant and services.
    ```console
    $ cd ./machine
    $ vagrant up
    $ cd /opt/docker
    $ docker-compose up -d
    ```
2. The following services will become available.
    * my_nginx (`access_log`s are forwared into journald): http://localhost:18080
    * fluent-bit: takes logs from journald and forward these into elasticsearch.
    * elasticsearch: http://localhost:9200 / http://localhost:9300
    * kibana: http://localhost:5601

## See

- [http://fluentbit.io/documentation/current/output/elasticsearch.html](fluent-bit/elasticsearch)
- [http://fluentbit.io/documentation/current/input/systemd.html](fluent-bit/systemd & journald)
