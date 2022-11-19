# csharp DateTime.UtcNow is not correct utc


```csharp
string utc1 = DateTime.UtcNow.ToString();
string utc2 = DateTime.UtcNow.ToString("o");

Console.WriteLine(utc1); 
// 2022/11/19 下午 12:42:59
// It's not quite right.

Console.WriteLine(utc2); 
// 2022-11-19T12:42:59.8101801Z
```

## reference

* [DateTime.UtcNow and DateTime.Now returned wrong time (2017)](https://stackoverflow.com/questions/47914350/datetime-utcnow-and-datetime-now-returned-wrong-time)

    > You try to clear cache on the `CultureInfo`, but `CultureInfo` holds a language and sometimes a country. That is not enough to give time zone since some countries span more than one time zone. You must search the info elsewhere. What does `TimeZoneInfo.Local.ToString()` return? As others asked, how do you format your `DateTime`? What does `DateTime.Now.ToString("o")` give? With "o" you will see a time zone hint (related to `TimeZoneInfo.Local`) when the DateTime instance has `.Kind` equal to `Local`. Supply more information to us.