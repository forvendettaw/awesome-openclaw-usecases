---
name: stock-watcher
description: 自选股监控Skill。管理个人股票watchlist，支持添加、删除、列出股票，汇总近期表现。使用10jqka.com.cn数据。适用于自选股管理、日常监控。
---

# 自选股监控

> 管理并监控自选股

## 定位

管理个人股票 watchlist，监控实时行情和重要公告。

## 触发条件

用户提到：
- 自选股
- 股票监控
- 持仓管理
- 股票提醒

## 功能

### 1. Watchlist 管理

```bash
# 添加股票
stock-watcher add NVDA

# 删除股票
stock-watcher remove NVDA

# 列出所有自选
stock-watcher list
```

### 2. 行情监控

- 实时价格
- 日涨跌幅
- 成交量

### 3. 提醒设置

```bash
# 价格提醒
stock-watcher alert NVDA --above 200

# 涨跌幅提醒
stock-watcher alert NVDA --change 5%
```

## 使用示例

```
用户: 添加 NVDA 到自选
→ 添加成功

用户: 我的自选股今天怎么样
→ 获取所有自选股行情 → 汇总表现

用户: NVDA 跌破180提醒我
→ 设置价格提醒
```

## 数据源

- 美股：Yahoo Finance
- A股：10jqka.com.cn

---

## 协同Skills

- `stock-analysis`: 股票分析
- `smallcap-scanner`: 小市值扫描
