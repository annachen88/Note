# Note
## Chapter 1
###### 祕密通訊概論
**Transposition 密碼法**: 調動字元的位置。  
**Substitution Cipher 替代密碼法** 又稱作“Caesar Cipher / Caesar Shift Cipher”  
**Cryptanalysis 密碼分析學** - **Frequency Analysis 頻率分析法**：回推密碼。透過文中字母出現的次數，對照字母統計被使用的頻率。 
* 1-2 加密技術 對稱式金鑰
  * Transposition Cipher : Rail-fence Cipher 籬笆密碼法 (破解使用Brute Force暴力法，當N個字元時，有N! 的可能性)  
      * **加密手法：將字元分為兩組，基數與偶數，最後前後組合一起。**
  *  Substitution Cipher : Caesar Cipher 凱薩密碼法 屬於 Mono-alphabetic Substiution密碼法的一種。  
      * **加密手法：對應字元表26個字母，取代為其他的英文字母。**
  *  Substitution Cipher : Vigènere Cipher 屬於 Poly-alphabetic Substiution密碼法的一種。  
      * **加密手法：對應字元表，根據給定金鑰字元對應訊息字元、取代為其他的英文字母。**
  *  Homophonic Substitution Cipher 等價替代密碼法：對付Frequency Analysis，不容易回推。   
      * **加密手法：將字元轉換成數字，並依照出現次序有所不同。**
* 1-3 Vigènere Cipher - Poly-alphabetic Substiution 介紹
  * 改善 Mono-alphabetic Substiution 的 Caesar Cipher。
  * 根據 Vigènere 密表(為Caesar密表的延伸)加密，事先約定金鑰來決定使用哪些列加密。
  * 特點：不顯露出字元重複的痕跡、頻率。
  * Kasiski Test 破解
    原理：找出相同的字母串，得知金鑰詞、長度，以透過單、複數字母的頻率分佈圖掌握。
    因此，增加金鑰長度，增加破解的難易度。
* 1-4 Sherlock Holmes and the Dancing Men 福爾摩斯和跳舞小人
  * 以小人形狀呈現，將同樣的形狀推敲出英文字母單字。 
## Chapter 2
###### 電腦病毒
* 2-1 病毒起源
  * 1949年 John Von Neumann發表的論文提到「可以自我複製的程式」。
  * 「Core Wars」遊戲被認為電腦病毒起源，如同「Imp Programs」程式小，容易複製、不易發現，消滅機率低。
    * 遊戲玩法：兩人各寫一個程式，載入同一電腦記憶體執行，程式互相驅趕對方在記憶體留下的暫存資料。被攻擊時會**自我複製**，等到其中一方程式被消滅。**（防毒軟體也是同一個精髓，使用一支病毒消滅另一支）**
  * 程式類型
    * 有機程式 Organism Programs 破壞程式，讓對方程式無法操作
    * 阻礙程式 Dwarf Programs 將記憶體部分位置改為零，使無法操作
    * 爬行程式 Creeper Programs 複製自己，覆蓋目標之記憶體資料
    * 收割程式 Reaper Programs 負責清除Creeper Programs留下之資料
* 2-2 病毒種類
  * 特性：不易發現、傳播速度快、型態多樣（不同路徑傳播）、資訊損害大（CIH病毒格式化）。
  * 病毒生命週期
    * 孕育創造期：複製病毒碼，切割小存於不同磁碟區，呼叫時才喚起執行。
    * 散佈寄居期：逃避防毒軟體的偵測。
    * 啟動發作期：特定日期執行、毀損硬碟。
    * 消滅除根期：防毒軟體控制消滅病毒。
  * 傳統型病毒
    * 檔案型病毒：附著在執行之程式檔案（CIH、13 Friday、SUNDAY、936、Aids2、兩隻老虎）
    * 開機型病毒：隱藏在Boot Sector啟動磁區、Partition Table硬碟分割表。（Monkey、DISK、KILLER、FISH、NOVENBER 4）
    * 巨集型病毒Macro Viruses：附著在Word Excel等（LoveLette、Cap、TaiwanN.O.1）
  * 綜合型病毒：結合惡意程式的Cyberplagues網路瘟疫
    * 1990年代開始，病毒作者製作工具組（Virus Creation Kit/Virus Generator），透過單選點擊即可創造病毒（木馬、網蟲、攻擊、惡意程式）
    * 主要指Virus、Worm、Trojan Horse、Attack Tool等四種特徵  
      * Virus & Worm 均可感染電腦及透過網路傳播（Worm寄身程式碼中，透過網路自發性散佈至主機中。Virus人為儲存裝置中，被動性擴散）
      * Trojan Horse假裝做某些事，無法透過網路自發性感染、不會自我複製，透過人為不知情複製執行執行暗藏工作（破壞資料、圓端遙控、偷竊密碼）
* 2-3 病毒防治
  * 特徵：檔案異常、不尋常訊息出現、執行速度變慢
  * 防治方法：
    * 病毒碼過濾法：根據病毒某一部分特徵（識別碼）
    * 加值總合法：將原始程式總和加值檢查、循環重複、影像計算檢查 **需確定原程式無毒** 
* 2-4 病毒實務分析
  * **Rootkit 權限工具箱**竊取最高權限之工具箱，可以讓攻擊者隱匿身份，入侵的系統分為：Windows/Linux-like/Unix分為**核心模式（Kernel-mode）** 透過特殊權限直接進入CPU操作指令、**使用者模式(User-mode)** 使用者權限影響系統運作、安全機制
  * Rootkit種類
    * AFX Windows Rootkit - User-mode
    * FU Rootkit - Kernel-mode
    * Header Defender - User-mode
  * Rootkit隱藏原理
    * 一般利用Hook來修改程式功能 分為三種：
      * API(Application Program Interface) Hook : 讀取動態連結資料庫的檔案Dynamic Link Library DLL檔，修改位置進入表Import Addess Table,IAT或匯出表Export Address Table,EAT 導入Rootkit
      * SSDT(System Device Dispatch Table) Hook : 將SSDT（系統裝置傳遞表）上的執行呼叫函式改成 Rootkit，易發現
      * DKOM(Direct Kernel Object Manipulation) : 可以在和核心中隱匿程序、網路連結、程式驅動、提升權限
  * 偵測Rootkit是否植入
    * Netstat指令 : 顯示TCP/IP的網路連接狀態 `netstat -an` 顯示所有連線、位置、監聽的連接阜
    * Pslist : 顯示程序、連結訊息 `-d`執行緒 `-m`記憶體 `-x`程序、記憶體、執行緒 `-t`程序樹狀圖 `-s`工作管理員
    * Psservice : 透過本機或遠端列出控制系統的工具 `-u` username `-p`password ...
    * RootkitRevealer : 掃描登入檔、本地磁碟區域尋找
  * Rootkit產生的紀錄：**1)IP、網路卡資訊 2)連線資訊 3)惡意程式本身 4)數位行為 **
  * 
## Chapter 3
## Chapter 13
## Chapter 14
## Chapter 15
