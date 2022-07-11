## Flowcharting介紹
Grafana的插件之一。需先使用draw.io將需要的圖表畫出來，例如：系統監控圖、網路拓樸圖、技術架構圖等，都可以利用[draw.io](https://app.diagrams.net/)在線上快速製出圖表並匯出XML、PDF、PNG等類型，draw.io也是一款免費且開源的繪圖工具。<br>
flowcharting可以將draw.io產出圖表的各個元素綁定數據資料，再藉由設定不同閥值、搭配不同顏色，使用者一眼就能清楚地看出各個服務或裝置的狀態，提升排查除錯的效率。<br> 
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/example.png)
*[圖片來源](https://grafana.com/grafana/plugins/agenty-flowcharting-panel/*)

## 操作與設定
#### Step1.繪圖
flowcharting的使用順序跟其他插件不太一樣，需要先繪圖再輸入數據。由於需要用到的多是流程圖或是架構圖，且輸入須為XML的格式，所以建議使用[draw.io](https://app.diagrams.net/)進行繪製，繪製完畢選擇輸出為XML，並將XML完整複製。
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/drawio.png)

#### Step2.匯入Grafana
(安裝指令```grafana-cli plugins install agenty-flowcharting-panel```)<br>
開啟Grafana panel，視覺化選擇flowcharting，點開右側選單Flowchart，將Source Content預設的XML清除並貼上Step1製作的XML，左邊就會載入圖表了。<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/basic%20setting.png)
-Edit Draw：線上編輯圖形<br>
-Prettify：增加XML換行，使其更易閱讀<br>
-Minify：將XML的行數減少<br>
-Compress/Encode：將XML加密<br>
-Extract/Decode：解碼XML<br>
<br>
#### Step3.設定資料來源
每個繪製好的元素都可以綁定數據，所以需要新增資料或是監控來源。根據需求在qeury下指令，並在Ailas設定名稱，以便後續使用。<br>
如果query的設定相似也可點選藍色框框的按鈕複製再行修改。
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/source.png)
<br>
#### Step4.設定圖形顯示
點選右側選單Mapping，開始進行數值的綁定及圖片顯示的設定。<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/setting-1.png)
Options<br>
-Rule name：規則名稱<br>
-Apply to metrics：要綁定的資料源(會出現Step3設定過的Ailas)(也支援正則表達)<br>
-Aggregation：資料來源的聚合<br>
Type<br>
-Type：類別<br>
-Unit：單位<br>
-Decimals：保留小數的位數<br>
<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/setting-2.png)
Thresholds用來設定圖形展示的顏色變化<br>
-Invert：倒序排列<br>
-Gradiant：漸層色<br>
-Icon state：顯示警示狀態<br>
<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/setting3.png)<br>
Tooltips開啟後，將滑鼠移動到圖形上，會自動顯示監控值<br>
Graph Tooltips開啟後，可設定彈出圖形產生的效果<br>
<br>
#### Step5.將資料綁定圖形
將要呈現的資料綁定到相對應的圖形
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/setting4.png)
Color/Tooltip Mappings：處理顏色顯示<br>
Label/Text Mappings：處理數值對應、query結果<br>
綁定的方式可以透過圖形的id(可在選單inspect查詢或修改)或label，也可以點選上圖中1的按鈕，變色後再點選想要綁定的圖形，就會將該圖形的id傳送到what裡<br>
-When：觸發時間<br>
-How：填充型態或內容<br>
<br>
最後再將其他圖形所需的Rule設定好即可
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/flowcharting/finall.png)
