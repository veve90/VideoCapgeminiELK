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
sudo systemctl start docker
sysctl -w vm.max_map_count=262144
sudo docker pull sebp/elk
sudo docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -it --name elk sebp/elk
```
### Start ELK docker

https://developers.redhat.com/blog/2016/06/07/how-to-install-elastic-stack-elk-on-red-hat-enterprise-linux-rhel/ 

## Demo
### Montrer les données pour la demo
```
{
	"venue": {
		"venue_name": "Lavender MRT Station",
		"lon": 103.841484,
		"lat": 1.289644,
		"venue_id": 23389692
	},
	"visibility": "public",
	"response": "yes",
	"guests": 0,
	"member": {
		"member_id": 98130812,
		"photo": "https:\/\/secure.meetupstatic.com\/photos\/member\/1\/4\/f\/2\/thumb_126845362.jpeg",
		"member_name": "LOO CHOON BOON"
	},
	"rsvp_id": 1662954951,
	"mtime": 1491964070655,
	"event": {
		"event_name": "Nature cafe @Aperia mall ",
		"event_id": "239125933",
		"time": 1493116200000,
		"event_url": "https:\/\/www.meetup.com\/TRAVEL-LEISURE-CARE\/events\/239125933\/"
	},
	"group": {
		"group_topics": [{
			"urlkey": "hiking",
			"topic_name": "Hiking"
		},
		{
			"urlkey": "diningout",
			"topic_name": "Dining Out"
		},
		{
			"urlkey": "travel",
			"topic_name": "Travel"
		},
		{
			"urlkey": "adventure",
			"topic_name": "Adventure"
		},
		{
			"urlkey": "group-fitness-training",
			"topic_name": "Group Fitness Training"
		},
		{
			"urlkey": "nature-walks",
			"topic_name": "Nature Walks"
		},
		{
			"urlkey": "outdoors",
			"topic_name": "Outdoors"
		},
		{
			"urlkey": "photo",
			"topic_name": "Photography"
		},
		{
			"urlkey": "cycling",
			"topic_name": "Cycling"
		},
		{
			"urlkey": "dating-and-relationships",
			"topic_name": "Dating and Relationships"
		},
		{
			"urlkey": "social",
			"topic_name": "Social"
		},
		{
			"urlkey": "excercise",
			"topic_name": "Exercise"
		},
		{
			"urlkey": "community",
			"topic_name": "Community"
		},
		{
			"urlkey": "international-travel",
			"topic_name": "International Travel"
		},
		{
			"urlkey": "socialnetwork",
			"topic_name": "Social Networking"
		}],
		"group_city": "Singapore",
		"group_country": "sg",
		"group_id": 14057192,
		"group_name": "TRAVEL, LEISURE & CARE  (TLC)",
		"group_lon": 103.85,
		"group_urlname": "TRAVEL-LEISURE-CARE",
		"group_lat": 1.3
	}
}
```

### l'API de meetup
http://stream.meetup.com/2/rsvps

### Start docker
```
sudo systemctl start docker
sysctl -w vm.max_map_count=262144
sudo docker pull sebp/elk

sudo docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -it \
    -e ES_HEAP_SIZE="2g" -e LS_HEAP_SIZE="1g" -e LS_OPTS="--no-auto-reload" \
    --name elk sebp/elk
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
