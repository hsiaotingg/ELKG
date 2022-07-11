### Flowcharting介紹
Grafana的插件之一。需先使用draw.io將需要的圖表畫出來，例如：系統監控圖、網路拓樸圖、技術架構圖等，都可以利用[draw.io](https://app.diagrams.net/)在線上快速製出圖表並匯出XML、PDF、PNG等類型，draw.io也是一款免費且開源的繪圖工具。<br>
flowcharting可以將draw.io產出圖表的各個元素綁定數據資料，再藉由設定閥值、配置顏色，讓使用者可以一眼清楚地看出各個服務的狀態，並且提升排查除錯的效率。<br> 
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/example.png)
*圖片來源:https://grafana.com/grafana/plugins/agenty-flowcharting-panel/*

### 操作與設定
##### Step1.繪圖
flowcharting的使用順序跟其他插件不太一樣，需要先繪圖再輸入數據。由於需要用到的多是流程圖或是架構圖，且輸入須為XML的格式，所以建議使用[draw.io](https://app.diagrams.net/)進行繪製，繪製完畢選擇輸出為XML，並將XML完整複製。
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/drawio.png)

##### Step2.匯入Grafana
開啟Grafana panel，視覺化選擇flowcharting，點開flowchart選單，將Source Content預設的XML清除並貼上剛才做好的XML，就會跑出圖表了。<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/basic%20setting.png)
-Edit Draw：線上編輯圖形<br>
-Prettify：格式化圖形代碼<br>
-Minify：合併圖形代碼<br>
-Compress/Encode：加密圖形代碼<br>
-Extract/Decode：解碼圖形代碼<br>
