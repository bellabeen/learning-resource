# Learning ELK

## Referensi 

- https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-elastic-stack-on-ubuntu-20-04


## How to Install Elasticsearch

- Install depedensis
  - curl -fsSL https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
  - add to source list *echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list* 
  - sudo apt update
  - sudo apt install elasticsearch
- sudo nano /etc/elasticsearch/elasticsearch.yml -> change **network.host** to **localhost**
- sudo systemctl start elasticsearch
- sudo systemctl enable elasticsearch
- Testing access **curl -X GET "localhost:9200"**
- Output
  ``` 
  {
  "name" : "node-1",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "8XDqe_rESLqF44gXKGUFeQ",
  "version" : {
    "number" : "7.3.0",
    "build_flavor" : "default",
    "build_type" : "deb",
    "build_hash" : "de777fa",
    "build_date" : "2019-07-24T18:30:11.767338Z",
    "build_snapshot" : false,
    "lucene_version" : "8.1.0",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
  }
  ```
- If get error *curl: (7) Failed to connect to localhost port 9200: Connection refused* -> check firewall add port 9200 for access
## How to Install Kibana

- Installl depedensis
  - sudo apt install kibana
  
- sudo systemctl enable kibana
- sudo systemctl start kibana

  