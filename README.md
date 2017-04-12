# VideoCapgeminiELK
Repository pour la video de 5 min de Capgemini sur ELK


## Slides
https://slides.com/alinagherman/elk-1

## Install sur Viperr
### Install docker
https://docs.docker.com/engine/installation/linux/fedora/#install-using-the-repository

### Install docker compose
https://docs.docker.com/compose/install/


## Demo


### Start docker
https://elk-docker.readthedocs.io/#elasticsearch-logstash-kibana-elk-docker-image-documentation 
https://developers.redhat.com/blog/2016/06/07/how-to-install-elastic-stack-elk-on-red-hat-enterprise-linux-rhel/ 

```
sudo systemctl start docker
sysctl -w vm.max_map_count=262144
sudo docker pull sebp/elk

sudo docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -it \
    -e ES_HEAP_SIZE="2g" -e LS_HEAP_SIZE="1g" -e LS_OPTS="" \
    --name elk_demo_cap sebp/elk
```

### L'image SEBP/ELK
* 5601 (Kibana web interface).
* 9200 (Elasticsearch JSON interface).
* 5044 (Logstash Beats interface, receives logs from Beats such as Filebeat – see the Forwarding logs with Filebeat section).

### Connection à la machine docker/ELK
```
sudo docker exec -it demo_elk /bin/bash
```
Copier la configuration meetup.conf dans /etc/logstash/conf.d

### 
