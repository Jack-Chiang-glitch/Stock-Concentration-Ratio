# Stock-Concentration-Ratio (Provide both Chinese and English versions of README.md.) <br>

想法 : 台股水池較小，所以跟著主力作贏面較大。<br>

去永豐金券商的官網爬取N日前15大買超券商數量以及前15大賣超券商資料， 相減之後，得到當天的淨買超或是淨賣超，<br>
再去yfinance爬取成交量，計算進N日總成交量，<br>
計算 籌碼集中度 = N日(淨買超 or 淨賣超) / N日(成交量)<br>
得到這樣的表格<br>
![image](https://github.com/user-attachments/assets/e891bbfa-5251-4df9-8087-e7cd418a54d2)

之後畫出N日籌碼集中度的圖(N=1,5,60,120)<br>
![image](https://github.com/user-attachments/assets/3738b31a-122e-4a4a-b20b-f71b9130b110)

策略 : <br>
#1.多頭排列：1日>5日>60日>120日 <br>
#condition = (SCR1>SCR5) & (SCR5>SCR60) & (SCR60>120)<br>
            
#1.多頭排列：1日>5日>60日<br>
#condition = (SCR1>SCR5) & (SCR5>SCR60)<br>

#4-2反種型態：5日>60日&120日<br>
#condition = (SCR5>SCR60) & (SCR5>SCR120)<br>

#4-3反種型態：60日>5日>120日<br>
#condition = (SCR60>SCR5) & (SCR5>SCR120)<br>

#2.空頭排列：1日<5日<60日<120日<br>
#condition = (SCR1<SCR5) & (SCR5<SCR60) & (SCR60<120)<br>

![image](https://github.com/user-attachments/assets/085ce539-273d-447b-b96d-a2f07df7a739)



Idea : <br>
Taiwan’s stock market has relatively lower liquidity, meaning that following institutional investors (主力) can offer a higher probability of success.<br>

The strategy involves web scraping data from E.SUN Securities to obtain the top 15 net-buying and net-selling brokers over the past N days. The net value is calculated by subtracting the net-selling from the net-buying.<br>
Then, trading volume is retrieved from Yahoo Finance (yfinance), and the total traded volume over N days is computed.<br>

The Stock Concentration Ratio (SCR) is calculated as follows:<br>
SCR = N-day Net Buying or Net Selling / N-day trading volume <br>
Trading Strategy : <br>
            
#1.Bullish Formation：1 day>5 day>60 day<br>
#condition = (SCR1>SCR5) & (SCR5>SCR60)<br>

#4-2 Reversal Formation：5 day>60 day&120 day<br>
#condition = (SCR5>SCR60) & (SCR5>SCR120)<br>

#4-3 Reversal Formation：60 day>5 day>120 day<br>
#condition = (SCR60>SCR5) & (SCR5>SCR120)<br>

#Bearish Formation：1 day<5 day<60 day<120 day<br>
#condition = (SCR1<SCR5) & (SCR5<SCR60) & (SCR60<120)<br>

