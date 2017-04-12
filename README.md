# VideoCapgeminiELK
Repository pour la video de 5 min de Capgemini sur ELK


## Slides
https://slides.com/alinagherman/elk-1

## Install sur Viperr
### Install docker
https://docs.docker.com/engine/installation/linux/fedora/#install-using-the-repository


### Install docker compose
https://docs.docker.com/compose/install/

### Start docker
https://elk-docker.readthedocs.io/#elasticsearch-logstash-kibana-elk-docker-image-documentation 

 *   5601 (Kibana web interface).
 *   9200 (Elasticsearch JSON interface).
 *   5044 (Logstash Beats interface, receives logs from Beats such as Filebeat – see the Forwarding logs with Filebeat section).

```
sysctl -w vm.max_map_count=262144
sudo systemctl start docker
sudo docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -it --name elk sebp/elk
```
### Start ELK docker


https://developers.redhat.com/blog/2016/06/07/how-to-install-elastic-stack-elk-on-red-hat-enterprise-linux-rhel/ 

## Demo
