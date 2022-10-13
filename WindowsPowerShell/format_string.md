# format string

```powershell
$name_array = "Penny", "Joson", "Runna"

foreach ($name in $name_array) {

    # 方法 1
	[string]::Format("Hello, {0}.", $name)

    # 方法 2
	"Hello, {0}." -f $name

    # 方法 3
	"Hello, $name."
}
```