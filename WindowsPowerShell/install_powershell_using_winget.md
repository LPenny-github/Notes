# Install PowerShell using Winget


## purpose

將目前的 PowerShell 從 5.x.x 升級至 7.2.6 。

## preparation

`$PSVersionTable`: 查詢版本與重要資訊。

## steps

1. `winget search Microsoft.PowerShell`: 藉由 Winget 來查詢目前提供的版本。

    假如這是查詢結果：

    ```
    Name               Id                           Version Source
    ---------------------------------------------------------------
    PowerShell         Microsoft.PowerShell         7.2.6.0 winget
    PowerShell Preview Microsoft.PowerShell.Preview 7.3.0.6 winget
    ```

1. `winget install --id Microsoft.Powershell --source winget`: 藉由 Winget 來安裝想要的版本。

## validation

1. 關閉目前開啟的 PowerShell。(視情況重新開機)

1. `$PSVersionTable`: 查詢版本與重要資訊。

## reference

* [Installing PowerShell on Windows / Install PowerShell using Winget (recommended)](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.2#install-powershell-using-winget-recommended)