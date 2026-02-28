---
name: earnings-tracker-cn
description: 财报速报Skill。追踪重点公司财报发布时间，自动获取财报要点，生成快速摘要。适用于财报季监控、投资决策支持。
---

# 财报速报

> 追踪并快速获取财报要点

## 定位

追踪重点公司财报发布时间，自动获取财报要点。

## 触发条件

用户提到：
- 财报
- 财报速报
- EPS
- 营收
- earnings call

## 功能

### 1. 财报日历

```python
# 获取财报日历
df = ak.stock_us_earnings_calendar()
```

### 2. 财报要点

```python
# 获取财报数据
df = ak.stock_us_financial_analysis()
```

### 3. 速报生成

```
📊 NVDA 财报速报 - Q4 2025

营收: $68.13B (+122% YoY)
EPS: $1.62 (+185% YoY)

要点:
- 数据中心收入增长 409%
- Q1 指引超预期
- 盘后涨 5%

AI 点评: 继续看好，目标价 $300
```

## 定时任务

```json
{
  "schedule": "0 8 * * 1-5",
  "name": "Earnings_Morning_Brief"
}
```

## 使用示例

```
用户: 这周有哪些公司财报
→ 获取财报日历 → 返回列表

用户: NVDA 财报怎么样
→ 获取财报数据 → 生成速报
```

---

## 协同Skills

- `stock-analysis`: 股票分析
- `stock-daily-analysis-cn`: 每日分析
