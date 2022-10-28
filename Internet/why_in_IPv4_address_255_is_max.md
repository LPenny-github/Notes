# Why in IPv4 address 255 is max? 

模糊的答案是 因為當時 可以/需要 上網的人比較少。

IP address 簡單來說是網路溝通時，你這台裝置的地址。

網路發展前期比較少人 可以/需要 上網，現在有更多上網的需求(因此地址的需求量大增)，所以自 IPv4 至 IPv6 可以服務更多裝置上網。 


## IPv4

n = 0-255 ((n.n.n.n) 以阿拉伯數字 10 進位表示)

2^8 = 256 (從 0 計算，所以範圍是 0-255)

```

(2^8) * (2^8) * (2^8) * (2^8) = 2^32 
                              = 4294967296 
                              (共有這麼多的網路位址可以提供)
```

例如:

* c# numeric types: byte (Unsigned 8-bit integer) = 0-255


## IPv6

x = 0-4,294,967,295 ((x.x.x.x.x.x.x.x) 以 16 進位表示)

2^32 = 4294967296

---

### 為何是 16 進位

```
2^128 = 2 ^ (4 * 8 * 4) 
          = 16^ (8 * 4) 
          = (16^4) * (16^4) * (16^4) * (16^4) * (16^4) * (16^4) * (16^4) * (16^4)
```
---

```
(2^32) * (2^32) * (2^32) * (2^32) = 2^128 
                                  = 340,282,366,920,938,463,463,374,607,431,768,211,456
                                    (約 3.4×10^38 網路位址)
```

例如:

* c# numeric types: uint (Unsigned 32-bit integer) = 0-4,294,967,295


## reference

* [Why is 255 the max IP?](https://qr.ae/pvlU5y)

* [Integral numeric types (C# reference) / Characteristics of the integral types](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types#characteristics-of-the-integral-types)