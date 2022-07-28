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
開啟panel，在視覺化選擇[Phlowchart]<br>
在這個插件的資料格式除了必須是JSON格式外，另外就是每一個方塊都需要九項如下圖資料，缺一不可。<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/9.png)<br>
**這邊的id很重要，會影響到關係連結source、target的部分**<br>
-type可以控制方塊顯示的內容 EX.twoTextFourNumber會顯示兩行文字+四個數字，oneTextOneNumber會顯示一行文字(title)、一個數字。<br>
-number一定是四個，沒有值也要填null<br>
-url可以自行放入需要的網站連結，不須連結網站也不可忽略此項<br>
#### Step3 設定資料連接方向
方塊之間的關係<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/relationship.png)<br>
這邊的id主要是讓自己方便辨別，不會影響方塊的關係方向<br>
-source是源頭<br>
-target是要指向的目標方塊<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/show%20relationship.png)<br>
將這兩個部份分別放在不同query<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/Phlowchart/pics/query.png)<br>
#### Step4 其他客製設定
右側選單有其他設定<br>
-Allow Dragging Of Nodes 開啟後可移動方塊<br>
-Show mini map 開啟後panel右下角會顯示一個簡易小圖顯示目前的視野位子<br>
*未完
