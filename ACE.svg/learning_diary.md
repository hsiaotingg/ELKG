## ACE.SVG

07/22<br>
目前可以將SVG圖匯入grafana呈現，但還不知如何控制各圖形以及綁定資料，只知道可能需要學習svg.js語法。User JS Render、User JS Init這兩個也須研究差異。網路上也找不到什麼介紹ACE.SVG這個插件的操作與介紹。<br>
將圖畫好後匯出SVG，Text setting選擇Convert labels to SVG<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/ACE.svg/pic/2.png)<br>
我選擇在網頁上開啟SVG檔，按F12將紅色框框這段複製下來<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/ACE.svg/pic/3.png)<br>
回到Grafana panel，點開SVG Document將剛剛複製的貼上，把User JS Render、User JS Init裡預設的內容整個刪除，圖就會出現了
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/ACE.svg/pic/1.jpg)

### SVG.js
07/23<br>
SVG.js是一個輕量級的JavaScript庫，可用來輕鬆操作SVG和定義動畫。<br>
SVG（Scalable Vector Graphics，可縮放向量圖形）是基於XML、用於描述二維向量圖形的一種圖形格式。SVG由W3C制定，是一個開放標準。<br>
SVG.js中包含了大量用於定義動畫的方法，如移動、縮放、旋轉、傾斜等，具體可參閱相關演示。<br>
