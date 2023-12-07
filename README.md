# beancount-template
A starter template for beancount

资产恒等式:

```
资产 Assets = 权益 Equity + 负债 Liabilities
```

## Install Beancount

`pip3 install beancount fava`

## Convert to Sqlite

`bean-sql main.bean ledger.db`

## Structure

```
--+
  +-- main.bean          // 主文件
  +-- assets.bean        // 定义资产
  +-- equity.bean        // 定义权益（净资产 Net Assets），通过 pad 和 balance 初始化资产账户
  +-- expenses.bean      // 定义开支
  +-- income.bean        // 定义收入
  +-- liabilities.bean   // 定义负债
  +-- /2022              // 按年度分类
  |     +-- jan.bean     // 按月度
  |     +-- ...
  +-- /2023
  |     +-- jan.bean
  |     +-- ...
  +-- ...
```

在 `main.bean` 中引入所有文件，语法：

`include "2022/jan.bean" ; 引入 2022 年一月记录`

> `;` 后为注释