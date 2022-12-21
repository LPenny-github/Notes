# tracert

診斷網路連線(異常)的工具之一，類似 `ping` 。


## Why it works

* 送出 ICMP (Internet Control Message Protocol) 封包，紀錄其 躍點 (hop) 數目、RTT (round-trip time) 和 IP。網路管理人員可藉由這些反饋資訊推測連線問題為何。

    * [tracert(...Windows Server/Windows Commands/Reference)](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/tracert)

### Example

```cmd
C:\Users\Hehe>tracert google.com

Tracing route to google.com [172.217.160.110]
over a maximum of 30 hops:

  1    10 ms    11 ms    11 ms  xxx.xxx.xxx.xxx
  2    11 ms    12 ms    10 ms  xxx.xxx.xxx.xxx
  3    12 ms    11 ms    11 ms  xxx.xxx.xxx.xxx
  4     *        *        *     Request timed out.
  5    11 ms    11 ms    10 ms  2xxx.xxx.xxx.xxx
  6    12 ms    12 ms    12 ms  xxx.xxx.xxx.xxx
  7    11 ms    11 ms    12 ms  xxx.xxx.xxx.xxx
  8    12 ms    11 ms    11 ms  xxx.xxx.xxx.xxx
  9    12 ms    10 ms    10 ms  tsa03s06-in-f14.1e100.net [172.217.160.110]

Trace complete.

C:\Users\Hehe>tracert 172.217.160.110

Tracing route to tsa03s06-in-f14.1e100.net [172.217.160.110]
over a maximum of 30 hops:

  1    10 ms    11 ms    11 ms  xxx.xxx.xxx.xxx
  2    12 ms    11 ms    11 ms  xxx.xxx.xxx.xxx
  3    12 ms    11 ms    11 ms  xxx.xxx.xxx.xxx
  4     *        *        *     Request timed out.
  5    12 ms    12 ms    14 ms  xxx.xxx.xxx.xxx
  6    12 ms    12 ms    12 ms  xxx.xxx.xxx.xxx
  7    13 ms    11 ms    10 ms  xxx.xxx.xxx.xxx
  8    13 ms    13 ms    13 ms  xxx.xxx.xxx.xxx
  9    11 ms    11 ms    11 ms  tsa03s06-in-f14.1e100.net [172.217.160.110

Trace complete.
```


## what `*` means

* 有些路由器不具備回傳資訊的的功能，但有時候 `*` 的出現模式可以協助判斷哪邊出包(即將丟包)：

    * > If you see a sudden increase in a hop and it keeps increasing to the destination (if it even gets there), then this indicates an issue starting at the hop with the increase. This may well cause packet loss where you will even see asterisks (*) in the report.

        ```
        1    10 ms     7 ms     9 ms  172.16.10.2
        2    78 ms   100 ms    32 ms  ip10-167-150-2.at.at.cox.net [70.167.150.2]
        3    78 ms    84 ms    75 ms  100ge7-1.core1.nyc4.he.net [184.105.223.166]
        4   782 ms   799 ms     * ms  10gr10-3.core1.lax1.he.net [72.52.92.226]
        5     * ms   899 ms   901 ms  10g1-3.core1.lax2.he.net [72.52.92.122]
        6   987 ms   954 ms   976 ms  205.134.225.38
        7  1002 ms  1011 ms   999 ms  www.inmotionhosting.com [192.145.237.216]
        ```

        * [How to Read a Traceroute](https://www.inmotionhosting.com/support/server/ssh/read-traceroute/)


## What is RTT

* 發出封包到收到確認對方收到封包的時間。

    * > In telecommunications, round-trip delay (RTD) or round-trip time (RTT) is the amount of time it takes for a signal to be sent plus the amount of time it takes for acknowledgement of that signal having been received.

    * > RTT is also known as ping time, and can be determined with the ping command.

        * [Round-trip delay(wiki)](https://en.wikipedia.org/wiki/Round-trip_delay)


## 有什麼問題是使用 tracert 無法釐清的

* 很多，像是 被擋 ip、雙方的閘道設定或雙方的防火牆。


## 其他參考

* [traceroute(wiki)](https://en.wikipedia.org/wiki/Traceroute)

* [What is RTT(Round Trip Time)?](https://www.geeksforgeeks.org/what-is-rttround-trip-time/)

