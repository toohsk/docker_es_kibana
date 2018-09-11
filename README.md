# docker_es_kibana

I use docker compose to build and manaage containers, ElasticSearch and Kibana.
And also, I installed japanese analyzer, kuromoji, in ElasticSearch Dockerfile for analyzing japanese text.
There is a template in `es/template` for setting analyzer.

## Before build containers

Before building containers and manage them, you need to prepare Docker environment.
For instance, I'm using `Docker for Mac` for Docker environment.

## How to use

Execute the command as follows to build and run containers.

```
$ docker-compose build
$ docker-compose up
```

If you want to kill containers, use `Ctrl-C`.

To set a template, use curl command.

```
curl -H "Content-Type: application/json" -XPUT localhost:9200/_template/<template_name>\?pretty --data-binary '@es/template/template.json'
```

### Note

If you `docker-compose up` once, docker's data volume will be created.
So that data created in ElasticSearch wouldn't be lost after kill ElasticSearch container.
So don't forget to remove data volume when you remove this repository.
Execute the command as follows to remove data volume.

```
$ docker volume rm docker_es_kibana_es-data
```