## 要怎麼解決「換新電腦的 SSH 問題」？

一、

1. 把舊電腦的 SSH 複製出來

1. 在新電腦 .ssh known_hosts 裡面加入帳戶提供者(這個網站)

二、

1. 為新電腦製作一個新的 SSH

1. 把這個新的 SSH 加入你的 GitHub 帳戶

1. 在新電腦 .ssh known_hosts 裡面加入帳戶提供者(這個網站)

---

# 如果我們採取方法二

## 在新電腦 .ssh known_hosts 裡面加入帳戶提供者(這個網站)

1. 打開 PowerShell。

1. 搜尋網頁 `GitHub's SSH key fingerprints`，記得查看網頁的安全性(瀏覽器網址前方有鎖頭標誌，點一下鎖頭標示看內容)。

1. (自選) PowerShell 指令 `ls  ~/.ssh`： 打開使用者目錄底下的 `.ssh` 資料夾。查看是否有已知的 host 紀錄或是已有私鑰和公鑰。因為是新電腦所以可能是空白。 

1. (自選承上) PowerShell 指令 `cat 檔案名稱`: 把檔案內容顯示在 PowerShell 上。

1. PowerShell 指令 `ssh -T git@github.com`: 測試連線至 GitHub。如果新電腦的 .ssh 檔案內未記錄該網站，那會出現文字提示你要不要把該網站加入:

```
The authenticity of host 'github.com (20.27.177.113)' can't be established.
ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
``` 
1. 複製公鑰 (即 `SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM` )，回到 網頁 `GitHub's SSH key fingerprints`，`crl + f` 看是否全部符合。是的話，填入 `yes` 然後按 `Enter`。接著會出現:

```
Warning: Permanently added 'github.com,20.27.177.113' (ECDSA) to the list of known hosts.
git@github.com: Permission denied (publickey).

```

## 為新電腦製作一個新的 SSH

1. PowerShell 指令 `ssh-keygen -t ed25519 -C "your_email@example.com"`: 建立新電腦的私鑰和公鑰，其中 `-C "your_email@example.com"` 是非必要的，如果這一串不打，系統也會幫你自動生成。建立成功會顯示:

```
Generating public/private ed25519 key pair.
Enter file in which to save the key (~/.ssh/id_ed25519):
```

2. 按照指示按 Enter 存檔。然後系統會問你要不要再加上密碼鎖:

```
Enter passphrase (empty for no passphrase):
```

3. 不要加密就直接按 `Enter`，要就打密碼然後 `Enter`。

4. 系統再次確認加密事宜，同上。公私鑰生成成功之後，會顯示在 PowerShell 上。

5. (自選) PowerShell 指令 `ls ~/.ssh`，可以看到三個檔案，副檔名為 `.pub` 者為公鑰:

```
id_ed25519
id_ed25519.pub
known_hosts
```

## 把這個新的 SSH 加入你的帳戶的 SSH Agent

1. 登入你的 GitHub 帳戶 > Settings > SSH and GPG keys

1. 按 `New SSH keys`，打入 `id_ed25519.pub` 裡面的內容，不含後面自動生成很像 email 的那段。

1. GitHub 帳戶密碼再度確認。成功後畫面畫出現先增的 SSH。

1. PowerShell 指令 `ssh -T git@github.com`: 測試連線至 GitHub。成功連線的話會出現:

```
Hi 你的GitHub帳戶名稱! You've successfully authenticated, but GitHub does not provide shell access.
```

## Ref

* [GitHub's SSH key fingerprints](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints)

* [Checking for existing SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)

* [Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
 
* [Testing your SSH connection](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection)


