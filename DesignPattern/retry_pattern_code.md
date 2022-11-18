# Retry pattern (code)


## code example

```csharp
private int retryCount = 3;
private readonly TimeSpan delay = TimeSpan.FromSeconds(5);

public async Task OperationWithBasicRetryAsync()
{
  int currentRetry = 0;

  for (;;)
  {
    try
    {
      // 你想做的事
      await TransientOperationAsync();

      // 包在 try 或 while 裡，必須 break 或 return
      break;
    }
    catch (Exception ex)
    {
      // 告知操作失敗，或是紀錄嘗試次數
      Trace.TraceError("Operation Exception");

      currentRetry++;

      // 達到嘗試次數上限或是遇到非短暫錯誤就放棄 retry
      if (currentRetry > this.retryCount || !IsTransient(ex))
      {
        // 告知結果
        throw;
      }
    }

    // 再次 retry
    await Task.Delay(delay);
  }
}
```


```csharp
private bool IsTransient(Exception ex)
{
  if (ex is OperationTransientException)
    return true;

  var webException = ex as WebException;
  if (webException != null)
  {
    // 自訂值得再度嘗試的錯誤情境
    return new[] {WebExceptionStatus.ConnectionClosed,
                  WebExceptionStatus.Timeout,
                  WebExceptionStatus.RequestCanceled }.
            Contains(webException.Status);
  }

  return false;
}
```


## reference

* [Retry pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/retry?fbclid=IwAR2Q7W6isc5XLoReZ89y55Xh5SaD3f7vOCAyIvRanKEAvTpGw08GgIqbU-w#example)