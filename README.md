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

