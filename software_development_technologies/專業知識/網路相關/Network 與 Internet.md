
## Network
計算機網絡是一組互相連接的計算機和其他設備，它們通過有線或無線方式共享資源和數據。

---
## Internet
網際網路又稱互聯網指一個全球範圍內的計算機網絡系統，由數以百萬計的私有、公共、學術、企業和政府網絡互相連接而成。

---
## 通訊協定

### OSI 模型
#### OSI 簡介
開放式系統互聯模型（Open System Interconnection Model）， 簡稱為OSI模型。

1. 由國際標準化組織 **ISO** 所提出的概念模型
2. 整體資料流程分為 **7** 個分層
3. 高層（第 5 層 到 第 7 層）越偏向軟體，低層（第 1 層 到 第 4 層）則偏向硬體。
4. 每個中間層為其上一層提供功能，自身功能則由其下一層提供

#### OSI 層級架構

![[osi_structure.png]]

#### OIS 層級定義
##### 第七層：應用層
 **主要功能**：處理應用程式。
提供使用者網路應用服務，專指為應用軟體而設計的介面，以設定與另一應用軟體之間的通訊。
	
**常見的通訊協定**：
1. DHCP（Dynamic Host Configuration Protocol）
2. FTP（File Transfer Protocol）
3. HTTP（HyperText Transfer Protocol）
4. POP3（Post Office Protocol-Version 3）

> 第七層的應用軟體（網路瀏覽器、電子郵件、線上遊戲、即時通訊等）透過單一或多種通訊協定傳達資料，依據不同的網路服務方式，這些協定能定義各自的功能及使用規範等細部規則，像是網路瀏覽器藉由HTTP的溝通，即可呈現出完整的網頁。  
> 這些和使用者最貼近且直接的應用軟體就屬於第七層應用層的規範。

##### 第六層：表示層
 **主要功能**：轉檔編碼。
```
資料透過網路傳輸時，需要將內容予以加密或解密，而這個過程就屬於展示層。
```
	
**常見應用**
SCII、JPEG、MIDI、 SSL...等

##### 第五層：會議層
**主要功能**：數據傳輸中設定和維護電腦網路中兩台電腦間的通訊連接。
```
此層級負責建立網路連線使得電腦間得以傳輸資料， 等到資料傳輸結束時，連線將會中斷。
```

**常見應用**：
- NetBIOS ：
- SSH：
- TLS：

##### 第四層：傳輸層
**主要功能**：將傳輸表頭併入資料形成封包，負責整體電腦整體的資料傳輸及控制。

```
傳輸層可以將一個較大的資料切割成多個8位元組表示的資料流來傳輸， 替模型頂端的第五、六、七等三個通訊層提供流量管制及錯誤控制。 傳輸控制協定（Transmission Control Protocol，簡稱TCP） 則是最長見具有傳輸層功能的協定。
```

**TCP**：
```
將資料流分割成適當長度的報文段(受該電腦連接的網路資料鏈路層的最大傳輸單元限制）。 TCP為了保證不發生丟包， 因此會給每個封包序號，同時序號也保證了傳送到接收端實體的包的按序接收。 然後接收端實體對已成功收到的包發回一個相應的確認資訊（ACK）， 如果傳送端實體在合理的往返時延（RTT）內未收到確認， 那麼對應的封包就被假設為已遺失並進行重傳。
```

##### 第三層：網路層
**主要功能**：提供路由及定址功能，將網路表頭加至數據包，形成封包，以便在網路間傳遞。

```
主要的通訊協定是網際網路協定（Internet Protocol，IP）目的主要是為這筆資料定下傳送目的地的位址 資料在傳輸時，該協定將IP位址加入傳輸資料內，並把資料組成封包（Packet）。 在網路上傳輸時，封包裡面的IP位址會告訴網路設備這筆資料的來源及目的地。 由於網路層主要以IP運作為主，故又稱為「IP層」。
```

**IPv4**：
**IPv6**：

##### 第二層：資料連結層
**主要功能**：負責網路尋址、錯誤偵測和改錯，為網路之間建立邏輯連結。
```
資料連結層將實體層的數位訊號封裝成一組符合邏輯傳輸資料，這組訊號稱為資料訊框（Data Frame）。 訊框內包含媒體存取控制（Media Access Control，MAC）位址、 邏輯鏈路控制(Logical Link Control, LLC) 兩部分。 而資料在傳輸時，這兩項資訊可讓對方主機辨識資料來源。
```

**子層**：
- **媒體存取控制 MAC**：
```
主要工作：資料幀的封裝/卸裝、定址和識別、接收與傳送、差錯控制、鏈路的管理。

位址格式：
	由48個位元(6個位元組)構成
	以16進位的方式來表示 

MAC子層的存在消除了不同物理鏈路種類的差異性
```

- **邏輯鏈路控制 LLC**：
```
主要工作: 控制訊號的交換、資料的流量
解釋上層通訊軟體傳來的命令並產生回應
克服資料在傳送的過程中所可能發生的種種問題(資料發生錯誤、重覆資料...)
```

> MAC和IP一樣，都是提供「定址」的方式，好讓各個設備了解網路資料應該要往什麼地方發送。MAC的位址都是唯一的，所有的網路卡都有一個MAC位址，而這個位址不會與世界上其他的網路卡的MAC位址相同
> MAC主要負責控制與連線物理層的物理介質。在傳送資料的時候，MAC協議可以事先判斷是否可以傳送資料，如果可以傳送將給資料加上一些控制資訊，最終將資料以及控制資訊以規定的格式傳送到物理層；在接收資料的時候，MAC協議首先判斷輸入的資訊並是否發生傳輸錯誤，如果沒有錯誤，則去掉控制資訊傳送至LLC層。

##### 第一層：實體層
**主要功能**：區域網路上傳送資料框，負責管理電腦通訊裝置和網路媒體之間的互通。
```
硬體： 針腳、線纜、電壓值、集線器、中繼器、網卡、主機介面卡...等
```

### TCP／IP 通訊協定
#### TCP／IP 簡介
總共歸類到4個抽象的層中。  
每一抽象層建立在低一層提供的服務上，並且為高一層提供服務。

- 第四層：應用層
- 第三層：傳輸層
- 第二層：網際網路層
- 第一層：鏈路層

#### TCP／IP 資料傳遞流程
1. 資料從應用層透過TCP或UDP埠到達傳輸層，並決定使用TCP或UDP協定來存取網路。
2. 到網際網路層後，IP協定會提供如何將資料導引到正確的邏輯IP位址的資訊。
3. 進入網路存取層後，會透過上層的ARP及RARP協定來轉換IP位址和實際位址
4. 將資料格式化成能在傳輸線上傳輸的格式而送出。
5. 最後資料離開了原始端電腦傳向目的端，而該電腦收到後，則進行相反之步驟。

**流程圖**
![[tcpip_flow.jpg]]

####  TCP／IP 層級定義
##### 第四層：應用層
 **主要功能**：利用基礎網路交換應用程式專用的資料的協定，協同所有應用程式工作。

```
TCP/IP最頂層，其中的應用軟體並沒有明確規範的工作類別 像是偵測網路資訊的工具或是提供一些網路的服務： FTP、DNS...等等。 

處理過程：

資料從網路相關的程式以這種應用內部使用的格式進行傳送，然後編碼成標準協定的格式， 一旦從應用程式來的資料編碼成一個標準的應用層協定，它將傳送到傳輸層。 

一些特定的程式也被視爲在此層運行，直接提供服務給使用者應用。
```

##### 第三層：傳輸層
**主要功能**：傳輸層是一個提供應用程式和網路之間的介面。

```
只有IP位址的話，若有不同的應用軟體要同時進形網路傳輸，所有資料就會從同一個出口一起出去而產生混亂的碰撞情形，因此有了連接埠的產生，可以讓一台電腦同時擁有好幾個對外連接的出口，這也使得網路傳輸有了多工的能力。
```

##### 第二層：網際網路層
**主要功能**：將資料從源網路傳輸到目的網路，並選擇路徑。

##### 第一層：鏈路層
**主要功能**：規定資料的傳輸方式，讓網路傳輸有規範及效率

**運作方式**：
```
實際上並不是網際網路協定組中的一部分， 它是封包從一個裝置的網路層傳輸到另外一個裝置的網路層的方法。 添加報頭準備傳送、 將資料轉換成一稱為訊框(Frame)的格式，並將其轉為可用電子流或類比脈衝表現的樣式。 通過實體媒介實際傳送資料達成鏈路功能。 但也可能是一個虛擬專有網路（VPN）或者隧道， 在這裡從網路層來的包使用隧道協定和其他（或者同樣的）協定組傳送而不是傳送到實體的介面上。 VPN和通道通常預先建好，它們有一些直接傳送到實體介面所沒有的特點（加密經過它的資料）。 另一端，鏈路層將完成資料框接收、去除報頭並且將接收到的包傳到網路層。
```

## TCP／IP 與 OSI  比較
### 共通性：
同許多其他協定一樣網路傳輸協定也可以看作一個多層組合，每層解決資料傳輸中的一組問題並且向使用這些低層服務的高層提供定義好的服務。高層邏輯上與使用者更為接近，所處理資料更為抽象，它們依賴於低層將資料轉換成最終能夠進行實體控制的形式。

兩者都基於獨立的協議棧的概念，強調網路技術獨立性（Network Technology Independence）和端對端確認（End-to-End Acknowledgement）。

且層的功能大體相同，兩個模型能夠在相應的層找到相應的對應功能。

### 比較圖

|TCP／IP|OSI|功能|協定或設備|
| :--:|:--:|:--:|:--:|
|應用層|應用層|處理應用程式，提供使用者網路應用服務|HTTP、HTTPS、FTP、SMTP、DNS|
||表示層|轉換資料的表達方式，加密或解密資料|ASCII、JPEG、MIDI、SSL|
||會議層|建立和終止網路連線，管理會話|NetBIOS、SSH、TLS|
|傳輸層|傳輸層|提供端到端的通信和數據傳輸控制，確保數據可靠傳輸|TCP、UDP|
|網際網路層|網路層|決定資料的路徑選擇和轉發，加入網路位址|IPv4、IPv6、ICMP|
|鏈路層|資料連結層|在網路之間建立邏輯連結，處理流量控制和錯誤偵測|MAC、LLC|
||實體層|在物理媒介上傳送數位訊號|電纜、光纖、無線信號|
