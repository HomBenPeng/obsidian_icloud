
---
## Introduction HTML

### What is HTML？
- [HTML](https://en.wikipedia.org/wiki/HTML) 全名為 「超文本標記語言」（ HyperText Markup Language），是建立網頁標準的 Markup Language，HTML 不是程式語言。
- HTML 主要工作是**描述網頁結構**。

###  HTML Overview
- **Developed by：** WHATWG
- **Filename extension：** `.html` 、 `.htm`
- **Latest release：** [Living Standard](https://html.spec.whatwg.org/multipage/)

---
##  Introduction CSS

###  What is CSS
- [CSS](https://en.wikipedia.org/wiki/CSS) 全名為 「層疊樣式表」（Cascading Style Sheets），「層疊」（Cascading）的意思 CSS 是有 **優先順序的規則**。
- CSS 主要工作是告訴  HTML Element 的**樣式規則**（如 標題、顏色、寬度 ... 等）。

### CSS Overview
- **Developed by：** W3C
- **Filename extension：** `.css`
- **Latest release：** CSS3

---
## Introduction JavaScript（JS）

###  What is JavaScript
- [JavaScript](https://en.wikipedia.org/wiki/JavaScript)（簡稱 JS）是一種程式語言。
- JavaScript 主要工作是透過更新或改變 HTML 和 CSS 讓網頁更具有互動性，（如 點擊按鈕顯示彈出視窗、即時更新網頁內容 ... 等）。

### JavaScript Overview
- **Designed by：** [ECMAScript](https://en.wikipedia.org/wiki/ECMAScript "ECMAScript") standard
- **Filename extension：** `.js`、`.cjs`、`.mjs`
- **Stable release：** ECMAScript 2024

---
## 總結
### HTML、CSS、JavaScript 三者的關係

| 技術 | 角色 | 主要工作 |
| :--- | :---: | :--- | 
| HTML | 結構 | 定義內容和框架 |
| CSS | 樣式 | 控制外觀和佈局 |
| JavaScript | 行為 | 添加互動和動態功能 |

### 合作方式

- **HTML：** 是網頁的基礎，CSS 和 JavaScript 都是以 HTML 作為基礎來操作。
- **CSS：** 改變 HTML 的樣式。
- **JavaScript：** 可以動態修改 HTML 和 CSS。
---
## See also

### 程式語言必須具備以下條件
- **語法規則**（Syntax Rules）
- **邏輯運算**（Logical Operations）
- **數據類型**（Data Types）
- **變數與常數**（Logical Operations）
- **函數與副程式**（Functions and Subroutines）
- **輸入與輸出**（Input and Output）
- **錯誤處理**（Error Handling）
- **擴展性**（Extensibility）

### Living Standard 與 Recommendation 

**總結比較**

|      | Living Standard | Recommendation |
|:---: | :---: | :---: | 
|組織   | WHATWG | W3C |
|更新速度| 快 | 慢 |
|穩定性   | 不穩定、動態 | 穩定、固定 |

**結論**
- **Living Standard** 適合追求最新技術、願意承擔不確定性的開發者或團隊，比如網頁技術的前沿探索者。它與瀏覽器廠商緊密結合，反映了「現實優先」的哲學。
  
- **Recommendation** 適合需要穩定基礎、長期規劃的場景，比如企業應用或教育資源。它重視共識和互操作性，代表「標準優先」的傳統模式。

### HTML Development History 

#### 1990 年代：HTML的發明與標準化
1.  **1990 年：** HTML的發明 Tim Berners-Lee 在[歐洲核子研究中心]發明了HTML，並編寫了第一個網頁瀏覽器和網頁伺服器軟體。
2. **1993 年：** [IETF](https://en.wikipedia.org/wiki/Internet_Engineering_Task_Force) 發布了第一個 HTML 規範草案，由 Tim Berners-Lee 和 Dan Connolly 撰寫。
3. **1994 年：** [W3C](https://en.wikipedia.org/wiki/World_Wide_Web_Consortium) 成立，開始負責HTML的標準化工作。
4. **1994 年：** IETF 成立 HTML 工作小組，負責進一步開發和標準化 HTML。
5. **1995 年：** IETF 發布HTML 2.0規範，成為第一個正式的 HTML 標準。
6. **1996 年起：** W3C負責HTML定義及維護。

####  2000 年代初：WHATWG 的成立
1. **2000 年：** W3C推動[XHTML](https://en.wikipedia.org/wiki/XHTML)
    - W3C開始推動XHTML並計劃開發XHTML 2.0。這個新標準的目的是使HTML更加嚴謹和結構化，以符合XML的規範。
2. **2004 年：分歧的出現**
    - **XHTML 2.0** 的規範過於嚴格，與現有的 Web 技術和開發實踐不兼容，這引起了瀏覽器廠商和開發者的不滿。他們認為 XHTML 2.0 的嚴格規範會帶來開發上的困難，並阻礙 Web 技術的靈活性和創新。
3. **2004 年：WHATWG 成立**
    - 由 Apple、Mozilla 和 Opera 等主要瀏覽器廠商聯合成立了 [WHATWG](https://en.wikipedia.org/wiki/WHATWG)，並立即主導HTML5的開發。
    - WHATWG 的目標是創建一個更靈活、更適合現代 Web 應用的標準，並確保向後兼容，避免 XHTML 2.0 的嚴格規範對開發者造成的負擔。

#### 2007 年 到 2014 年：共同發布發布HTML5
4. **2007 年：** W3C 開始跟 WHATWG 合作
	- W3C 意識到 XHTML 2.0 的方向不被業界接受，因此決定重新關注 HTML 的發展，並與 WHATWG 合作，將 HTML5 作為未來的 Web 標準。
5. **2008 年：** [HTML5 Wikipedia](https://en.wikipedia.org/wiki/HTML5) 公開草案
	- WHATWG 發布了 HTML5 的第一個公開草案，W3C 也開始基於 WHATWG 的工作制定 HTML5 的正式標準。
6. **2014 年：** HTML5 成為推薦標準
	- W3C 宣布 HTML5 成為正式的[[Introduction：HTML、CSS、JavaScript#Recommendation|Recommendation]]。
	- WHATWG 則繼續以[[Introduction：HTML、CSS、JavaScript#Living Standard|Living Standard]]的模式更新 HTML5。

#### 2019 年： W3C 將 HTML 開發權移交給WHATWG 
7. **2019 年：** W3C 移交 HTML 開發權
	- W3C 和 WHATWG 宣布，HTML 標準的開發權將完全移交給 WHATWG，W3C 不再單獨發布 HTML 版本。
	
#### 總結 
8. **WHATWG：** 
	- 取代W3C成為制定HTML標準的組織，負責HTML的開發，並以Living Standard方式更新。
9. **W3C：** 
	- 退出制定 HTML 標準後，轉為專注其他 Web 技術（如 CSS、SVG、WebAssembly 等）的標準化工作。

## References

### 網際網路工程任務組：Internet Engineering Task Force

### Living Standard 
**What is Living Standard：** 爲 WHATWG 採用，是一種 **持續更新、動態演進的標準**。

**好處**
- **跟上技術進步**：網頁技術發展很快，像新的功能（比如 WebRTC 或 Canvas）需要快速融入標準。如果用傳統方式，可能會落後於實際應用
- **減少版本混亂**：過去有 HTML4、XHTML、HTML5 等版本，容易讓人搞不清楚什麼是最新的。用 Living Standard 就只有一個「當前標準」，隨時保持最新。
- **與瀏覽器同步**：主流瀏覽器（像 Chrome、Firefox、Safari）都參與 WHATWG，他們會根據這個標準實作功能，開發者和標準制定者能更緊密合作。

**壞處**
- **瀏覽器相容性風險：** 雖然瀏覽器廠商參與 WHATWG，但每個瀏覽器實作新功能的進度不同。如果 Living Standard 更新太快，有些瀏覽器可能來不及跟上，導致網頁在不同瀏覽器上的表現不一致。

### Recommendation
**What is Recommendation：** 爲W3C採用，從標準制定到最終階段，代表該標準已被認為是穩定、成熟，並且可以用於實際應用的正式規範。

**好處**
- 穩定性：達到 Recommendation 階段的標準被視為穩定，意味著在未來不會有重大的改變。這對開發者和業界來說很重要，因為他們可以依賴這些標準來開發長期的應用。
- 瀏覽器相容性：一旦成為 Recommendation，其他組織、瀏覽器製造商、軟體開發者等通常會開始或加速對其的支援和實作。

**壞處**
- **更新緩慢：** Recommendation 的制定過程需要經過多個階段，加上廣泛的社群審查和共識，這使得標準的更新速度很慢。在快速發展的網頁技術領域，這可能導致
- **靈活性不足：** 一旦發佈標準，標準基本上被「鎖定」，很少會有大的改動。這雖然保證了穩定性，但也意味著如果發現問題或需要新功能，只能等下一個版本

**W3C 標準制定過程**
10. Working Draft（工作草案）：這是標準開發的初始階段，任何人都可以參與討論，提出意見。
11. Candidate Recommendation（候選推薦）：此階段，標準已經夠成熟，可以開始實際測試和實作，看看是否有需要調整的地方。
12. Proposed Recommendation（提議推薦）：在經過足夠的實作和測試後，如果沒有重大問題，標準會進入這個階段，準備最終被批准。
13. W3C Recommendation：這是標準的終點，標誌著該標準被認為足夠穩定和準備好被廣泛使用。它經過了廣泛的審查、實作和測試。

---
## External links

### HTML Related
1. [HTML WHATWG Official English](https://html.spec.whatwg.org/)
2. [HTML Wikipedia English](https://en.wikipedia.org/wiki/HTML)
3. [HTML Wikipedia Chines](https://zh.wikipedia.org/zh-tw/HTML)
4. [HTML W3C Official En](https://www.w3schools.com/html/default.asp)
5. [W3C Chines](https://www.w3school.com.cn/html/html_attributes.asp)
6. [HTML5 Wikipedia English](https://en.wikipedia.org/wiki/HTML5)
7. [HTML5 W3C Chines](https://www.w3school.com.cn/html/html5_intro.asp)
8. [菜鳥教程 HTML](https://www.runoob.com/html/html-tutorial.html)
9. [IETF Wikipedia English](https://en.wikipedia.org/wiki/Internet_Engineering_Task_Force) 
10. [Living Standard](https://html.spec.whatwg.org/multipage/)

### CSS Related
1. [CSS](https://en.wikipedia.org/wiki/CSS)

### JavaScript Related
1. [JavaScript](https://en.wikipedia.org/wiki/JavaScript)
2. [ECMAScript](https://en.wikipedia.org/wiki/ECMAScript "ECMAScript")