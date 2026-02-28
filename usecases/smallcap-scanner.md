---
name: smallcap-scanner
description: 小市值股票扫描Skill。每小时扫描X(Twitter)上的小市值股票机会，追踪KOL观点，聚合多源信息生成机会报告。适用于美股小市值投资机会发现。
---

# 小市值股票扫描

> 扫描 Twitter 上的小市值股票机会

## 定位

每小时扫描 X (Twitter) 上的小市值股票机会，追踪 KOL 观点。

## 触发条件

用户提到：
- 小市值
- 小盘股
- 股票机会
- KOL 观点
- 低市值

## 功能

### 1. KOL 追踪

追踪账号：
- @aleabitoreddit
- @crux_capital_
- @SJCapitalInvest
- 等

### 2. 扫描条件

- 市值：$500M - $5B
- 关注领域：
  - AI/科技
  - 光模块
  - 国防
  - 生物医药

### 3. 输出报告

```markdown
## 🚨 小市值扫描 - 2026-02-28

### 🔥 焦点: $AAOI

@aleabitoreddit: 看到 $25B 市值
@crux_capital_: 目标 $100+

### 📌 其他提及
- $AMPX: 无人机
- $XLE: 能源
```

## 定时任务

```json
{
  "schedule": "0 * * * *",
  "name": "SmallCap_Scanner_Hourly"
}
```

## 使用示例

```
用户: 有什么小市值机会
→ 扫描最近KOL推文 → 聚合机会 → 报告

用户: $AAOI 怎么看
→ 搜索相关KOL观点 → 汇总分析
```

---

## 协同Skills

- `stock-analysis`: 股票分析
- `tech-equity-research`: 科技股投研
