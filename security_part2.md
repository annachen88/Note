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
###### 網路安全協定
* IPSec Internet Protocol Security IP安全通訊原則
  基於TCP的機制，在傳送遺失封包（包含IP位置、主體資料）時，會再次傳送。  
  分為兩種傳送模式**「傳輸模式」IP位置傳輸安全，雙方能直接執行IPSec，封包及標示及來源目的位置。**    
  **「隧道模式」不需直接執行IPSec，傳送、接收在路由器、夾道Gateway的New IP Header建置下保護封包避免洩露IP位置**    
  * 不同於一般安全保護機制 特色：
    * 以OSI設計為基礎，因此應用程式可執行此安全服務
    * IP傳送封包具獨立性
    * 不需特意訓練使用者或升級應用程式(包容性)
    * 有end to end的安全機制，可抵擋網路攻擊
* VPN的安全通訊協定包含：
    * **IPSec**
      運作三個部分：**支援IP封包內相關資料、通訊參數安全而設計**
      * **AH (Authentication Header) 對訊息來源做鑑定Hash-md5/SHA**
        * 加解密演算法：CBC--->3DES IDEA RC-5 CAST-128 Blowfish
        * 訊息鑑定演算法：MD5、SHA、Tiger
        * HASH函數實作MAC--->HMAC-MD5-96、 HMAC-SHA-96、HMAC-Tiger-96
      * **ESP (Encapsulation Security Payload) 具有保護資料、資料來源鑑定功能、加密**
      * **IKE (Internet Key Exchange) 雙方取得金鑰的一致性，執行過程自動交換密、鑰，提供不同協定ISAKMP、Oakley、SKEMI**  
    * **L2F**：
      非同步的網路傳輸ATM Asynchronous Transfer Mode
    * **PPTP**:
      為PPP Point-to-point的延伸，連線可直接以ISP 所提供的的網路連線，能鑑定訊息來源並加密傳送
    * **L2P**
* IPSec 運作：以ip的封包方式傳送，因此與IP封包格式相關包含IPv6 IPv4，新版對密碼安全機制有關，分別採用對稱、公開金鑰密碼、HASH函數達到密碼機密性。  
**IPv4 總長160位元 來源ip-32位元 目的ip-32位元.**  
**IPv6 總長320位元 來源ip-128位元 目的ip-128位元.**  
![image](https://github.com/annachen88/Note/blob/dd1224f0452cb3aed57eea1ccd0406461d3eff88/IPSec.png)
* SA Security Association：當一部電腦傳送至另一部電腦時需要建立的連線，建立安全關係。
## Chapter 15
