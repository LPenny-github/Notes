# ping

診斷網路連線(異常)的工具之一。

就像打出一顆智慧桌球，這顆桌球可以記錄一些資訊，當這顆球回到你桌上時，你可以根據桌球紀錄的資訊來猜測，為何你和你的球友無法順利玩一局桌球。


## Why it works 

* 送出 ICMP (Internet Control Message Protocol) 封包，紀錄其 往返時間、TTL (Time To Live) 和狀態。網路管理人員可藉由這些反饋資訊推測連線問題為何。

    * [ping(...Windows Server/Windows Commands/Reference)](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/ping)

### Example

```cmd
C:\Users\Hehe>ping google.com

Pinging google.com [142.251.43.14] with 32 bytes of data:
Reply from 142.251.43.14: bytes=32 time=22ms TTL=58
Reply from 142.251.43.14: bytes=32 time=14ms TTL=58
Reply from 142.251.43.14: bytes=32 time=14ms TTL=58
Reply from 142.251.43.14: bytes=32 time=13ms TTL=58

Ping statistics for 142.251.43.14:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 13ms, Maximum = 22ms, Average = 15ms

C:\Users\Hehe>ping 142.251.43.14

Pinging 142.251.43.14 with 32 bytes of data:
Reply from 142.251.43.14: bytes=32 time=13ms TTL=58
Reply from 142.251.43.14: bytes=32 time=12ms TTL=58
Reply from 142.251.43.14: bytes=32 time=14ms TTL=58
Reply from 142.251.43.14: bytes=32 time=14ms TTL=58

Ping statistics for 142.251.43.14:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 12ms, Maximum = 14ms, Average = 13ms
ping 
```


## What is ICMP

* 基於網路協定製作出的診斷工具。

    * > 網際網路控制訊息協定（英語：Internet Control Message Protocol，縮寫：ICMP）是網際網路協定套組的核心協定之一。它用於網際網路協定（IP）中傳送控制訊息，提供可能發生在通訊環境中的各種問題回饋。通過這些資訊，使管理者可以對所發生的問題作出診斷，然後採取適當的措施解決。

        * [網際網路控制訊息協定(wiki)](https://zh.m.wikipedia.org/zh-tw/%E4%BA%92%E8%81%94%E7%BD%91%E6%8E%A7%E5%88%B6%E6%B6%88%E6%81%AF%E5%8D%8F%E8%AE%AE?fbclid=IwAR3NDB26ISSNhXoqHiEBG1Xta_RmzNQUw-kb09vJEvYmc16uNltjFYMhgxc)


## What is TTL

* 如果沒有停止機制的話，原本塞車的狀況可能會進階成癱瘓。

    * > 存活時間（英語：Time To Live，簡寫TTL）是電腦網路技術的一個術語，指一個封包在經過一個路由器時，可傳遞的最長距離（躍點數）。每當封包經過一個路由器時，其存活次數就會被減一。當其存活次數為0時，路由器便會取消該封包轉發，IP網路的話，會向原封包的發出者傳送一個ICMP TTL封包以告知躍點數超限。其設計目的是防止封包因不正確的路由表等原因造成的無限循環而無法送達及耗盡網路資源。

        * [存活時間(wiki)](https://zh.m.wikipedia.org/wiki/%E5%AD%98%E6%B4%BB%E6%99%82%E9%96%93?fbclid=IwAR0IjZbWeoSkWrh-Zb7Qfx83xfMNOxXGA4WEiQH5ufgaypYBkFLpCiFfmR0)


### How many TTL do I have

TTL 的數目是根據電腦的作業系統自動設定的。


## 有什麼問題是使用 ping 無法釐清的

很多，例如：你自己的防火牆、對方一律封鎖 ping 的請求、對方鎖你 ip、雙方的閘道設定......。

不過網路連線診斷工具也不只有 ping。

偵查網路連線問題就像是玩一場偵探遊戲。