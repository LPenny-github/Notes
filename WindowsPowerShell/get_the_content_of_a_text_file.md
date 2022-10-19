# get the content of a text file


## purpose

讀取內含中文的文字檔：`chores_list.txt`

    ```
    整理雜物 100
    洗衣服 100
    清地板 100
    倒垃圾 100
    刷馬桶 100
    洗洗手槽 100
    換除濕劑 100
    清冷氣濾網 100
    清電風扇 100
    洗濾水壺 100
    ```

## solution

1. (這個括號內的文字都是廢話。如果這行不寫點什麼，下面 powershell code preview 就無法正常顯示。)

    ```powershell
    [System.IO.File]::ReadAllLines(".\chores_list.txt", [System.Text.Encoding]::UTF8)
    ```

2. (這個括號內的文字都是廢話。同上。)

    * 請參考：[Get-Content](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.2)

    ```powershell
    Get-Content -Path .\chores_list.txt -Encoding UTF8
    ```

## FYI

* 不同版本、平台 可能出現編碼差異：
    
    * [分享幾個在 Windows 與 Linux 常見的編碼問題與解決方案](https://blog.miniasp.com/post/2021/08/05/Character-Encoding-Problems-for-Windows-and-Linux)