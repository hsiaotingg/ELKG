## Pholochart
### 介紹
由飛利浦公司開發的插件，類似Flowcharting，需使用Infinity作為datasource，資料格式須為json，可直接在Grafana操作介面輸入資料，或是將資料放置於網站上以URL方式匯入。
<br>
### 操作
#### Step1 安裝Phlowchart、Infinity插件
安裝Phlowchart指令
```grafana-cli plugins install philipsgis-phlowchart-panel```<br>
安裝Infinity指令
```grafana-cli plugins install yesoreyeram-infinity-datasource```<br>
安裝後來到Grafana首頁，點選[configuration]<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/configuration.png)<br>
按[Add data source]<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/add%20data%20source.png)<br>
在搜尋框輸入[infinity]並選擇infinity<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/enter.png)<br>
點選後會出現資料設定，這邊先不需設定，按[Save & test]<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/set.png)<br>
#### Step2 輸入資料
#### Step3 設定資料連接方向
#### Step4 其他客製設定
