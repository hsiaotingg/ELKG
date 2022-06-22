# ELK 與 Grafana 環境建置

## Elasticsearch 環境建置

1. `sudo apt update ; sudo apt-get update`
2. `sudo apt install apt-transport-https openjdk-11-jdk -y`
3. `java --version` (確認有無顯示JAVA版本)
4. `sudo vim /etc/environment`
>下方加入 `JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"`
5. `source /etc/environment`
6. `echo $JAVA_HOME`
7. `wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg`
8. `echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list`
9. `sudo apt-get update`
10. `sudo apt-get install elasticsearch -y`
11. `sudo systemctl start elasticsearch`
12. `sudo systemctl status elasticsearch`
13. `sudo vim /etc/elasticsearch/elasticsearch.yml`
>變更   network.host:0.0.0.0 <br />
>並加入   `discovery.seed_hosts: [ ] `
14. `sudo systemctl restart elasticsearch`
15. `sudo /usr/share/elasticsearch/bin/elasticsearch-reset-password -i -u elastic`
16. `curl -k -u elastic:密碼 -XGET "https://localhost:9200"`
17. 在瀏覽器網址列輸入 https://你的IP:9200/

## Logstash 環境建置
1. `wget https://artifacts.elastic.co/downloads/logstash/logstash-8.2.3-amd64.deb`
2. `sudo dpkg -i logstash-8.2.3-amd64.deb`
3. `sudo systemctl start logstash`
4. `sudo systemctl stop logstash`

## Kibana 環境建置
1. `wget https://artifacts.elastic.co/downloads/kibana/kibana-8.2.3-amd64.deb`
2. `sudo dpkg -i kibana-8.2.3-amd64.deb`
3. `sudo sh /usr/share/elasticsearch/bin/elasticsearch-certutil ca --pem` 之後按enter
4. `sudo -s` (如要退出root模式 ctrl+d)
5. `cp /usr/share/elasticsearch/elastic-stack-ca.zip /etc/kibana`
6. `cd /etc/kibana`
7. `sudo apt-get install unzip -y`
8. `unzip elastic-stack-ca.zip`
9. `cp /etc/elasticsearch/certs/http_ca.crt /etc/kibana/ca`
10. `chgrp kibana /etc/kibana/ca/*`
11. `chown kibana /etc/kibana/ca/*`
12. `/usr/share/elasticsearch/bin/elasticsearch-reset-password -i -u kibana_system` (設定ES密碼)
13. `sudo nano /etc/kibana/kibana.yml` (進入yml後把下方程式碼，直接貼在最上層)
  
```    
    server.host: "0.0.0.0"
    elasticsearch.username: "kibana_system"
    elasticsearch.password: "密碼要設定"
    server.ssl.enabled: true
    server.ssl.certificate: /etc/kibana/ca/ca.crt
    server.ssl.key: /etc/kibana/ca/ca.key
    elasticsearch.hosts: ["https://自己ip:9200"]
    elasticsearch.ssl.certificateAuthorities: [ "/etc/kibana/ca/http_ca.crt" ]
    elasticsearch.ssl.verificationMode: none
```

14. `sudo systemctl start kibana`
15. `sudo systemctl restart kibana`
16. 登入 https://自己ip:5601

## Grafana 環境建置
1.  `sudo apt-get install -y adduser libfontconfig1`
2.  `wget https://dl.grafana.com/enterprise/release/grafana-enterprise_9.0.0_amd64.deb`
3.  `sudo dpkg -i grafana-enterprise_9.0.0_amd64.deb`
4.  `sudo systemctl enable --now grafana-server`
5.  `systemctl status grafana-server.service`
6.  `sudo systemctl stop ufw`
7.  在瀏覽器網址列輸入 http://你的ip:3000

acvs
