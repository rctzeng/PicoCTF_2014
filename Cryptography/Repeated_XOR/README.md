# Repeated XOR
拿到一個[hex encoded的密文](encrypt.txt)，只知道是由XOR key加密的，key長度未知。

## Strategy
 1. 固定長度的key，同一位加密同個字母會得到同樣的答案
  * 計算兩個重複字母的差，key的長度一定會是這些差的最大公因數的因數
 2. 猜出key長度後，就能對key的每一位當作single XOR各自擊破
  * 測試所有可能ascii碼，key的這一位，就是能產生最多英文正常用字的那個

## Solve
詳見[solve.py](solve.py)，得`your flag is: 29a70d3fe359728436dde20c004879692776be22`
