建立日期：2025 / 01 / 22

## Docker 三大元件
1. 映像檔（Image）
2. 容器（Container）
3. 倉庫（Repository）

#### 說明：理解了三大核心概念，就理解了 Docker 的整個生命週期。


#### 1. 映像檔
#####  說明介紹：
1. Docker 映像檔是一個唯讀的模板，用於創建 Docker 容器。每個映像包含運行應用程式所需的所有文件，包括代碼、Runtime、依賴項目、資料庫和相關設定文件...等，一切開發所需要的環境設定。
	- **舉例：** 一個映像檔可以包含一個完整的 ubuntu 作業系統與環境，裡面僅安裝了 Apache 或使用者需要的其它應用程式。
2. 映像檔可以用來建立 Docker 容器。
3. Docker 提供了一個很簡單的機制來建立映像檔或更新現有的映像檔，使用者也可以從其他人那裡或倉庫下載一個做好的映像檔來直接使用。
4. Docker 在執行容器前需要本地端存在對應的映像檔，如果映像檔不存在本地端，Docker 會從映像檔倉庫下載（預設是 Docker Hub 公共註冊伺服器中的倉庫）。

##### 映像檔作用與功能：
1. **封裝應用**： 映像檔將應用程式及其依賴項目封裝成一個獨立的單位，確保在不同環境中運行時不會發生依賴問題。
2. **版本控制**：每個映像檔可以有多個 TAG，允許對不同版本的應用進行版本控制和管理。
3. **共享與重用**：可以在不同的 Docker 主機上拉取相同的映像檔，確保應用程式在不同環境中的一致性。
##### 映像檔目的：
1. **提高可移植性**：映像檔確保應用程式在開發、測試和生產環境中的一致性。
2. **簡化部署**：通過使用 映像檔，可以快速部署和更新應用程式。

#### 2. 容器
#####  說明介紹：
1. Docker 利用容器來執行應用。
2. 容器是從映像檔建立的執行實例。它可以被啟動、開始、停止、刪除。
3. 每個容器都是相互隔開的、保證平台的安全。
4. 可以把容器看做是一個簡易版的 Linux 環境（包括 root 使用者權限、程式空間、使用者空間和網路空間等）和在其中執行的應用程式。
 5. 映像檔是唯讀的，容器在啟動的時候建立一層可寫層在最上層。
##### 容器作用與功能：
1. - **資源隔離**：每個容器都有自己獨立的文件系統、網絡和進程空間，確保應用在隔離的環境中運行。
2. **輕量級**：容器共享宿主操作系統的核心，比虛擬機更輕量級，啟動速度更快。
3. **彈性擴展**：可以根據需求快速擴展或縮減容器數量，實現應用的彈性擴展。
##### 容器目的：
1. **提高效能**：由於容器的輕量級特性，可以在單一宿主上運行更多的應用實例。
2. **簡化測試與部署**：開發人員可以在本地創建容器並進行測試，然後將相同的容器部署到生產環境，確保一致性。

#### 2. 倉庫
#####  說明介紹：
1. 倉庫是一個存放映像檔的集合。有時候會把倉庫和註冊表混為一談，並不嚴格區分。實際上，註冊表上往往存放著多個倉庫，每個倉庫中又包含了多個映像檔，每個映像檔有不同的標籤。
2. 倉庫分別：公開或私有，允許用戶存儲、共享和管理映像檔。
	- 公開倉庫：最大的公開倉庫是 [Docker Hub](https://hub.docker.com/)，存放了數量龐大的映像檔供使用者下載。
	- 私有倉庫：使用者也可以在本地網路內建立一個私有倉庫。
3.  當使用者建立了自己的映像檔之後就可以使用 `push` 命令將它上傳到公有或者私有倉庫，這樣下次在另外一台機器上使用這個映像檔時候，只需要從倉庫上 `pull` 下來就可以了。
##### 補充：
 1. Docker 倉庫的概念跟 [Git](http://git-scm.com/) 類似，註冊伺服器可以理解為 GitHub 這樣的託管服務。

 ### 補充資料：
 #### Docker 三大核心概念補充
 #### 1. 映像檔－TAG（標籤）：
##### 標籤作用與功能
 1. **版本標識：**
	 - 每個 Docker 映像可以有多個標籤，每個標籤表示該映像的一個版本。標籤幫助區分不同版本的映像，便於管理和使用。
	 - 常用的標籤包括版本號（如 `v1.0`、`v2.0`）、狀態標籤（如 `latest` 表示最新版本）。
 2. **標籤命名：**
	 - 標籤是附加在映像名稱後面的，使用冒號分隔。例如，`myapp:latest` 表示名稱為 `myapp` 的映像的最新版本。
	 - 如果沒有指定標籤，默認使用 `latest` 標籤。
##### TAG 運作機制及功能
1.- **創建與使用標籤**：
    
    - 當你建立或推送 Docker 映像時，可以指定標籤。例如：
        
        sh
        
        ```
        docker build -t myapp:v1.0 .
        docker push myapp:v1.0
        ```
        
    - 這樣，映像 `myapp` 就帶有 `v1.0` 標籤，可以通過 `myapp:v1.0` 來引用這個特定版本。
        
- **拉取帶標籤的映像**：
    
    - 使用 `docker pull` 命令時，可以指定標籤來拉取特定版本的映像。例如：
        
        sh
        
        ```
        docker pull myapp:v1.0
        ```
        
    - 這將下載帶有 `v1.0` 標籤的 `myapp` 映像。
        
- **查看映像標籤**：
    
    - 可以使用 `docker images` 命令來查看本地映像及其標籤。例如：
        
        sh
        
        ```
        docker images
        ```
        
    - 這將列出所有本地映像及其標籤。
        
- **更新標籤**：
    
    - 可以給現有映像添加新的標籤。例如：
        
        sh
        
        ```
        docker tag myapp:v1.0 myapp:latest
        ```
        
    - 這將給 `myapp:v1.0` 映像添加 `latest` 標籤，使其成為最新版本。
##### 總結：    
Docker 的標籤機制提供了一種靈活且高效的映像管理和版本控制方式。通過合理使用標籤，可以提高映像的可維護性和可管理性。

 #### 2. 註冊表（Registry）：
 ##### 註冊伺服器的定義
註冊（Registry ）是一個存儲和分發 Docker 映像檔的服務器。它提供了集中存儲 Docker 映像的場所，使得用戶可以輕鬆地推送和拉取映像。

 ##### 註冊表作用與功能
 - **存儲 Docker 映像**：
    
    - 註冊表存儲用戶創建的 Docker 映像，這些映像可以包含應用程序及其運行所需的所有依賴。
        
- **版本控制**：
    
    - 支持映像的標籤（Tag）和版本管理，允許用戶管理不同版本的映像，確保應用程序的可追溯性和穩定性。
        
- **分發 Docker 映像**：
    
    - 用戶可以從註冊伺服器拉取映像以在本地運行，或將本地開發的映像推送到註冊伺服器，進行共享和分發。
        
- **安全控制**：
    
    - 註冊伺服器可以設置訪問控制和身份驗證機制，確保映像的安全性和隱私。
        
- **鏡像存儲**：
    
    - 提供公開的和私有的鏡像存儲庫。公開存儲庫允許任何人訪問，而私有存儲庫則需要適當的授權。
##### 主要例子
- **Docker Hub**：
    
    - Docker 官方提供的註冊伺服器，是最流行的 Docker 映像存儲和分發平台之一。用戶可以在 Docker Hub 上找到大量的公開映像，也可以上傳自己的私有映像。
        
- **私有註冊伺服器**：
    
    - 用戶可以設置自己的私有註冊伺服器來存儲和管理敏感的映像，常見的選擇包括 Docker Registry、Harbor 和 Nexus。
##### 註冊伺服器工作流程
- **推送映像到註冊伺服器**：
    
    - 開發者創建映像後，使用 `docker push` 命令將映像推送到註冊伺服器。例如：
        
        sh
        
        ```
        docker push myregistry/myimage:tag
        ```
        
- **從註冊伺服器拉取映像**：
    
    - 使用者可以使用 `docker pull` 命令從註冊伺服器拉取映像，然後在本地運行。例如：
        
        sh
        
        ```
        docker pull 
        ```
##### 總結：
註冊伺服器在 Docker 生態系統中扮演著存儲、管理和分發映像的重要角色。它確保了映像的可訪問性和安全性，並支持版本控制和用戶訪問管理。