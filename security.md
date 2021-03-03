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
## Chapter 3
## Chapter 13
## Chapter 14
## Chapter 15
