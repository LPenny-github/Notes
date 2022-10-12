# run a script


## purpose

執行自己轉寫的腳本(script)。


## preparation

1. check `ExecutionPolicy` first

    * `Get-ExecutionPolicy`: 取得你的執行設定

        * 為了安全起見，電腦預設為 `Restricted`: 僅允許個別指令，不允許執行 script。

            * 參見：[about_Execution_Policies/PowerShell 執行原則/restricted](https://learn.microsoft.com/zh-tw/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2#restricted)

    * `Set-ExecutionPolicy RemoteSigned`: (以管理員身分執行) 更改執行設定

        * `RemoteSigned`: 允許本機撰寫的未簽署 script。

            * 參見：[about_Execution_Policies/PowerShell 執行原則/remotesigned](https://learn.microsoft.com/zh-tw/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2#remotesigned)

2. write a script (自選)

    * 打開 Notepad，存成 `test.ps1`，內容如下：

        ```powershell
        $numbers = 1, 3, 5

        foreach($item in $numbers)
        {
	        Write-Host $item
        }
        ```

3. run your script (檔名承上)

    * `.\test.ps1`: 因為剛好在該目錄底下，所以簡寫為 `.`

    * `C:\Users\test.ps1`: 列完整路徑也行。

4. dala~

    ```
    1
    3
    5
    ```