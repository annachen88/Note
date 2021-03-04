## Chapter 13
###### 公開金鑰的基礎建設
* PKI : Public Key Intrastructure 公開金鑰 以CA（Certificate Authority）作為網路交易的公正第三人
   * **機密性 Confidentiality** ： 確保不被第三方擷取
   * **鑑別性 Authentication** ： 能確認彼此身份
   * **完整性 Integrity** ： 確定傳送資料沒被第三方更改
   * **不可否認性 Non-repudiation** ： 當發生爭分時，提供相關證明
* CA ：為一個公正單位確認使用者與公鑰間的關係，查驗申請人身份之正確。
  * CA架構的標準 - ITU-T提出 **X.509樹狀結構**，RCA認證CA使用者再向各CA申請（但當RCA被入侵，則架構失敗）因此有水平架構：任取不相關人員作認證。
  * 認證機制：運用RSA等技術，鑑定身份。
* **RSA原理 : 任取兩質數p、q，取Ｎ＝p * q，公開金鑰e ＝e與（q-1）＊(q-1)的最大公因數為1，私密金鑰d滿足`e*d = 1 mod(p-1)(q-1)`**
* PKI 未來預測：加入電子商務，簡化流程洽公時間，更加有效透鍋光纖、纜線、衛星進行電子商務。
* CA運作流程：
   * **申請憑證 -> 憑證審核 -> 發布憑證 -> 下載憑證 -> 其他管理憑證相互交換認證**
   * 憑證管理中心可**註銷憑證發布**
* 公開金鑰憑證內容包含：
   * 版本（X.509版本）、序號、簽章演算法、發行者、有效日期
   * 主旨（金鑰持有人資訊）
   * 發行者（管理中心）唯一識別碼
   * 金鑰持有人唯一識別馬
   * 自行擴充欄位
   * **憑證簽章演算法：數位簽章演算法（MD5、SHA）**
   * 簽章值：根據資料算出的值
* CRL Certificate revocation list憑證廢止清冊：尚未到期就被憑證頒發機構吊銷的數位憑證的名單。
* SSL通訊協定：瀏覽器與網路主機間通訊電子商務時，常使用PKI。
  * **瀏覽器對伺服器身份鑑別 流程： 電子商務傳送憑證至瀏覽器，作身份識別 -> 瀏覽器產生對稱金鑰 ->瀏覽器使用伺服器公鑰加密傳回主機 -> 
  有憑證的商務主機才能解開 -> 再利用該金鑰傳送訊息（SSL的安全交易)**
  ![image](https://github.com/annachen88/Note/blob/51c5b15994b6d6a91d0daea30edc8f55e5628c45/ssl.png)
* IC卡：在卡片先入為處理器之IC晶片 
  * 微處理器
    * CPU
    * Mask ROM (Read Only Memory)
    * RAM (Random Access Memory)
    * I/O
  * 記憶體
    * ROM (Read Only Memory)
    * PROM (Programable ROM)
    * EPROM (Erasable Programable ROM)
    * EEPROM (Electronic EPROM)
  * 存放 採階層式的檔案架構 Master File (MF)、Dedicated File (DF)、Elementary File (EF)
  * IC卡作業系統分為 
    * Java Card : Visa Card
    * Multos Card : Master Card
    * Global Platform 
* 自然人憑證：推動GPKI（Government Public Key Intrastructure），向管理中心GRCA(Governmernt Root Certification Authority)
 SCA(Subordinate CA)申請網路身份憑證，未來可直接報稅、繳款、駕照。 
## Chapter 14
## Chapter 15
