### Flowcharting介紹
Grafana的插件之一。需先使用draw.io將需要的圖表畫出來，例如：系統監控圖、網路拓樸圖、技術架構圖等，都可以利用[draw.io](https://app.diagrams.net/)在線上快速製出圖表並匯出XML、PDF、PNG等類型，draw.io也是一款免費且開源的繪圖工具。<br>
flowcharting可以將draw.io產出圖表的各個元素綁定數據資料，再藉由設定不同閥值、搭配不同顏色，使用者一眼就能清楚地看出各個服務或裝置的狀態，提升排查除錯的效率。<br> 
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/example.png)
*[圖片來源](https://grafana.com/grafana/plugins/agenty-flowcharting-panel/*)

### 操作與設定
##### Step1.繪圖
flowcharting的使用順序跟其他插件不太一樣，需要先繪圖再輸入數據。由於需要用到的多是流程圖或是架構圖，且輸入須為XML的格式，所以建議使用[draw.io](https://app.diagrams.net/)進行繪製，繪製完畢選擇輸出為XML，並將XML完整複製。
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/drawio.png)

##### Step2.匯入Grafana
(安裝指令```grafana-cli plugins install agenty-flowcharting-panel```)<br>
開啟Grafana panel，視覺化選擇flowcharting，點開右側選單Flowchart，將Source Content預設的XML清除並貼上Step1的XML，就會載入圖表了。<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/basic%20setting.png)
-Edit Draw：線上編輯圖形<br>
-Prettify：格式化圖形代碼<br>
-Minify：合併圖形代碼<br>
-Compress/Encode：加密圖形代碼<br>
-Extract/Decode：解碼圖形代碼<br>
<br>
##### Step3.設定資料來源
每個繪製好的元素都可以綁定數據，所以需要新增資料或是監控來源。根據需求在qeury下指令，並在Ailas設定名稱，以便後續使用。<br>
如果query的設定相似也可點選藍色框框圖示複製再行修改。
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/source.png)
