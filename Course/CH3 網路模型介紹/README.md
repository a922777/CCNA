1.  ISO 7運作原理

2.  TCP/IP運作原理

3.  網路模型PDU介紹

4.  示範 Encapsulation 與 Decapsulation

## OSI Model (網路模型七層)

	7	Application (應用層) 
	#Browser(Google,IE)，E-mail -> outlook -> SMTP,POP
	#檔案,印表,訊息,資料庫,與應用服務
	6	Presentation (表現層)
	#資料結構定義
	#資料加密,壓縮,與轉換服務
	#轉碼的過程
	
	5 	Session (交談層)
	#管理，溝通
	#對話控制
	#下載
	#10M
	#限速5M

	7,6,5 都是在應用層處理

	4	Transport (傳輸層)
	#決定如何傳送資料，定義資料要怎麼送(TCP,UDP)
	#終端對終端連線

	3	Network	(網路層)
	#IP
	#資料繞送

	2	Data Link (資料鏈結層)
	#Address (定址) MAC地址
	#訊框

	1	Physical (實體層)
	#定義網路媒介的特性 ->有線分為(銅軸,光纖)，無線網路
	#實體拓樸

## 第一層運作方式
	有線層
	1. 將資料轉換成訊號
	2. 傳送端將訊號送入傳輸媒介
	3. 自傳輸媒介讀入訊號
	4. 將訊號還原成訊號
	資料(010101) -> 發送器 -> 訊號狀態 -> 接收器 -> 資料(010101)
	1.發送器依據資料內容直接改變電位狀態,送出訊號。
	2.接收器收到訊號後,依據電位狀態還原出資料內容。

	無線層
	1. 將資料轉換成訊號
	2. 傳送端送出電磁波訊號
	3. 接收電磁波訊號
	4. 接收端將訊號還原成資料
	資料(010101) -> 調變器(發送端) -> 載波(正弦波) -> 解調器(接收端) -> 資料(010101)
	1. 發送端的載波產生器輸出正弦波訊號給調變器。
	2. 調變器依據資料內容改變正弦波訊號的物理特性,送出訊號。
	3. 解調器收到訊號後, 拿它跟正弦波訊號相比較, 過濾出物理上的變動。
	4. 解調器依據訊號物理特性上的變動, 還原出資料內容。
	# 透過載波的特性變化來承載資料

## OSI layers -Peer-to-peer communications
	Encapsulated (封裝)
	PDU:Protocal Data Unit (協定資料單位)
## 
	Host A                  Host B
				   Data
	Application  <------->  Application

				   Data
	Presentation <------->  Presentation

				   Data
	Session 	 <------->  Session

				  Segments
	Transport    <------->  Transport

				  Packets
	Network      <------->  Network

				  Frames
	Data Link    <------->  Data Link

				   Bits
	Physical     <------->  Physical

## OSI Model vs TCP/IP Model

	OSI Model						   TCP/IP Model

	7. Application
	6. Presentation     Application    Application
	5. Session			   Layers

	4. Transport						Transport
	3. Network			Data Flow		Internet
	2. Data Link		  Layers        Network
	1. Physical							 Access

主流網路、防火牆(1~4層)
SD-WAN(5~7層)
## TCP/IP Model 
	4. Application (TELNET/FTP/SMTP/DNS)
	3. Transport (TCP/UDP)						
	2. Network (IP)
	2~4為Protocols
	1. Physical+data link (ARPANET/SATNET/Packet radio/LAN)
	1 為Networks

2021/01/15

				

