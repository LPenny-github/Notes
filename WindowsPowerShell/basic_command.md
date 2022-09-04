# basic command

* create a directory: 
    * `New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"`
        * `-Path` 可略，新資料夾會建在當前位置（同 `-Path .`）

    * `New-Item -ItemType "directory" -Path "c:\ps-test\newfoldername"`
        * 把新資料夾的名稱寫在 path 裡面，即可忽略 `-Name`

* clean the screen: 
    * `clear`
    * `cls`
    * `Clear-Host`