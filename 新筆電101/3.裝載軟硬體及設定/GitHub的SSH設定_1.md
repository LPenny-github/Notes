## SSH 是什麼？

像是人們的健保卡號碼，可以用來辨別身分。

(其中一種方式是) 由演算法產生一組公鑰、私鑰。公鑰儲存在帳戶，私鑰自己收好。當雙方鑰確認身分時會拿來比對。

## 換新電腦會有什麼 SSH 問題？

你的新電腦不認識你的帳戶提供者，你的帳戶提供者不認識你的新電腦，導致你無法在新電腦對你的帳戶存取。

## 要怎麼解決「換新電腦的 SSH 問題」？

一、

1. 把舊電腦的 SSH 複製出來

1. 在新電腦 .ssh known_hosts 裡面加入帳戶提供者(這個網站)

二、

1. 為新電腦製作一個新的 SSH

1. 把這個新的 SSH 加入你的 GitHub 帳戶

1. 在新電腦 .ssh known_hosts 裡面加入帳戶提供者(這個網站)

## Ref

* [About SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)