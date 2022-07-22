## ACE.SVG

0722目前可以將SVG圖匯入grafana呈現，但還不知如何控制各圖形以及綁定資料，只知道可能需要學習svg.js語法。User JS Render、User JS Init這兩個也須研究差異。網路上也找不到什麼介紹ACE.SVG這個插件的操作與介紹。<br>
將圖畫好後匯出SVG<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/ACE.svg/pic/2.png)<br>
我選擇在網頁上開啟SVG檔，按F12將紅色框框這段複製下來<br>
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/ACE.svg/pic/3.png)<br>
回到Grafana panel，點開SVG Document將剛剛複製的貼上，把User JS Render裡預設的內容整個刪除，圖就會出現了
![image](https://github.com/hsiaotingg/ELKG/blob/Grafana-plugins/ACE.svg/pic/1.jpg)
