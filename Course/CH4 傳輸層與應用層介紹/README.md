1.  應用層介紹

2.  Segment and Reassemble 介紹

3.  Port Addressing原理介紹

4.  TCP 與 UDP 運作介紹

## Application Layer
	包含:DNS,Telnet,E-mail,DHCP,Web,FTP Server

## Application Layer - Web Service
	HTTP(web) Server <---Network---> client
	#HTML(Hyertext超文本,Markup標示,Language語言)
	HTTP:Hyertext Transfer Protocol(超本文傳輸協定)
	port:80

## DNS (Domain Name System)
	網域名稱(實際是ip再連接)
	EX:http://www.yahoo.com.tw
	Http:80
	DNS:53

## Application Layer - Email
	收信:POP3,IMAP4
	送信:SMTP (Simple Mail Transler Protocol)
	收信:POP (Protocol of Post)
	#把信收進Client端才能閱讀(可以離線閱讀)
	收信:IMAP4 (Internet Message Access Protocol V4)
	#on-line:必須是連線狀態
	#Web mail是使用IMAP4
	E-mail Server - MDA
	Mail User Agent (MUA)
	Mail Delivery Agent (MDA)
	Mail Transfer Agent (MTA)
	Agent 代理
	POP3 Server dest port:110
	SMTP Server dest port:25
	IMAP4 Server dest port:143
	SMTP Server dest port:25
	
## Application Layer - DHCP(動態IP的分配)
	DHCP (Dynamic Host Configuration Protocol)
	DHCP Client 發送一個 DHCP Discover (Broadcast)
	
	DHCP Client     DHCP Discover -->DHCP Server
				<-- DHCP Offer
					DHCP Request  -->
				<-- DHCP Acknowledge
	
	DHCP Offer:Host IP,SubnetMask,Gateway,Dns
	



	
	










