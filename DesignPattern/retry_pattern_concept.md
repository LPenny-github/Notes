# Retry pattern (concept)


## Situation

處理網路因常見、短暫的溝通失敗。


## Prethink

* 常見：前人智慧？

    * pattern

* 短暫：How do you know it?

    * error log

* 值得嗎？

    * 商業角度：划算嗎？

    * 技術角度：排隊是有用的(useful)、有效的(effective)嗎？


## Benefits

* 提前預備

* 使用前人智慧


## Expense/Risk

* 效能(你和它)

* 事情可能更糟

    * 價值判斷錯誤

    * 程式設計不良


## How to avoid it?

* 價值判斷

    * 划算嗎？

* 程式設計

    * error log 協助判斷

        * 排隊是有用的(useful)嗎？

            * 常見錯誤：timeout...

    * retry pattern

        * 有效的(effective)嗎

            * retry 次數

            * 每次 retry 前的等待時間(小心被當駭客)

            * 結構設計(retry 包 retry, retry 卡死)

                * 底層失敗後快速回覆上層

            * test your code

