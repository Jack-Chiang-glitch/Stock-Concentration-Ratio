# Stock-Concentration-Ratio (Provide both Chinese and English versions of README.md.)

去永豐金券商的官網爬取N日前15大買超券商數量以及前15大賣超券商資料， 相減之後，得到當天的淨買超或是淨賣超，
再去yfinance爬取成交量，計算進N日總成交量，
計算 籌碼集中度 = N日(淨買超 or 淨賣超) / N日(成交量)
得到這樣的表格
![image](https://github.com/user-attachments/assets/e891bbfa-5251-4df9-8087-e7cd418a54d2)

之後畫出N日籌碼集中度的圖(N=1,5,60,120)
![image](https://github.com/user-attachments/assets/3738b31a-122e-4a4a-b20b-f71b9130b110)

策略 : 
