1.  介紹HUB 運作原理

2.  介紹Switch 運作原理

3.  Collision Domain形成介紹

4.  Broadcast Domain 形成介紹

## CNA考試科目編號640-802
ICND1 (Interconnecting Cisco Networking Devices)
CCENT考1的內容
ICND2 實作

CCNA可以分2次考
CCENT考ICND1的內容 加考 ICND2 實作

## HOST (主機)
	用來跟網路設備連線(可以設定IP的都可以稱為主機)
	例如；PC，Network Printer

## Network Device (網路設備)
	Router，Switch，Hub

## Network Media (網路媒介)
	不同地方需要不同的網路媒介
	光纖，無線網路

## Hub (集線器)
	Ethernet 乙太網路
	上面的孔稱為 port
	RJ45 網路接口

## Share Bus(匯流排)
	是一種共享資料傳輸的通道

## Addressing (定址)
	MAC:48bit 24bit+24bit，vebdor code+流水號
	
## Send message in Hub
	Source (發送方)
	Destination (接收方)
	當傳一筆資料，每台電腦都會收到，再根據MAC位址，
	刪除資料，傳到對應的電腦上。

## Problem of Hub
	會產生碰撞(clooide)問題，
	當有兩台電腦同時傳送資料時，就會產生碰撞問題。
	碰撞再一起的資料稱為垃圾訊息(garbled message)，
	垃圾訊息還是會傳送到其他的電腦上。

## COLLISION DOMAIN(碰撞區域)
	會產生碰撞的區域

## Ethernet (CSMA/CD)
	解決碰撞的方法有哪些?
	碰撞會影響傳輸的效能，乙太網路會減少碰撞的次數，進而提升效能。
	1. CSMA (Carrier Sense Multiple Access)防止碰撞機制
	每台電腦上都有一個雷達(比喻)，偵測網路卡上，有沒有電腦在傳送資料，
	假設電腦A正在傳送資料，B也要，這時B就不能傳送，就可以避免碰撞的問題。
	多重存取 (Multiple Access)
	只要是在Share Bus上的電腦都可以傳送資料
	listen before transmitting 
	一開始先檢查Share Bus上有沒有電腦在傳送資料

	2. CD (Collision Detection)偵測碰撞機制
	假設A，B電腦同時傳送資料，碰撞已經無法避免，CD會讓碰撞提前發生
	，第三者會發送一個JAM的訊息，把兩個資料提前清除掉，等待一段時間再傳送，就可以縮短碰撞的時間。
	back of time，下一次要傳送的等待時間，時間是隨機的(Random)。
	A要傳送的時間，跟B要傳送的時間是不一樣的。

## Physical Addressing (實體位址MAC)
	每台電腦上都有一個MAC Addressing，MAC是獨一無二的，
	範例:AA-AA-AA-AA-AA-AA

	MAC Address
	cmd->ipconfig
	這時只會看到IP的資訊
	cmd->ipconfig /all
	如果要查詢MAC位只要加上 /all

## Encapsulated data (封裝資料)
	封裝:發送方跟接收方的MAC位址加到，封裝資料的前面。
	Destination Address | Source Address | DATA
	CC-CC-CC-CC-CC-CC | AA-AA-AA-AA-AA-AA | Encapsulated data
	封裝不只封裝MAC資訊，還會封裝其他資訊。

## Switch (交換機)
	外觀跟Hub類似
	設備外面會標示，這台設備是Hub or Switch
	Cisco 2960 Switch Layer 2
	Cisco 3560 Switch Layer 3
	Switch 外面有很多個port，可以連接電腦或是其他的設備。
	任意兩個port，都是獨立的Bus。
	當A,B,C電腦同時傳送資料，資料不會產生碰撞問題。

	Switch是利用MAC Table傳送資料，每個port都會有編號。
	MAC1,MAC2...MAC3
	port1,port2...port8
	情況一 : 假設Host1傳送資料到Host3，Host3的MAC位址會接到Host1的前面。

	情況二 : 當Host1傳送資料到Host8，但Host8還未分配MAC Table位址這時會產生Floading。
	Flooding:每個port都會送一個資料，這時的運作方式就會跟Hub相同。
	每台電腦收到資料後，會檢查上面的MAC位址跟自己的有沒有一樣，一樣就接收，不一樣就丟棄。

## Switch forwarding methods
	Store-and-forward
	先儲存，再傳送
	假設Switch接了兩台電腦A,B
	傳送時會先檢查(check)資料，再進行傳送，較謹慎，但效能比較低。
	Cut-through
	直接傳送資料，效能較好，但不會檢查傳送時資料有沒有發生錯誤。

## Broadcast message(廣播訊息)
	目的MAC:FF:...:FF 稱為廣播訊息
	目的IP:255.255.255.255
	廣播訊息特性:
	假設Host1要發送一個廣播訊息給所有機器，它的目的MAC都會是FF，
	當switch收到廣播訊息的時候，它無條件會將廣播訊息，傳送給其他電腦，
	這時所有的電腦都會接收這個廣播訊息 (Hi H1!)。

## Broadcast Domain(廣播區域)
	廣播區域:廣播訊息可以到達的地方

2021/01/12







