# Spin Bit

在 QUIC 工作組的設計討論中，最長的主題之一就是 Spin Bit，人們花費了數百封郵件和數百個小時來討論它。

Spin Bit 的支持者認為，兩個 QUIC 端點之間路徑上的運營商和人員需要有辦法來測量延遲。

反對者則反感此功能潛在的訊息洩露。

## Spinning a bit

客戶端和伺服器端這兩個端點都為每個 QUIC 連接維護旋轉值0或1，並且將為該連接發送的封包上的旋轉位設置為適當的值。

然後，在每一次往返時，連接雙方都翻轉這一 bit 的值。效果就是觀察者可以監視的那個位域中的1和0的脈衝。

僅當發送人不受應用程序或流控制的限制時，此觀察才有效，並且在網路上對封包進行排序可能會使封包意外出現。