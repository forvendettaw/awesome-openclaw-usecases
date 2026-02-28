---
name: stock-daily-analysis-cn
description: LLM驱动的每日股票分析系统。支持A股/港股/美股的技术面分析，生成AI决策建议。包含均线、MACD、RSI、乖离率等指标，输出买入信号评分。触发词：股票分析、分析股票、每日分析、技术面分析。
---

# 每日股票分析

> 基于 LLM 的 A/H/美股智能分析

## 定位

为 OpenClaw 提供多市场股票技术面分析和 AI 决策建议。

## 触发条件

用户提到：
- 股票分析
- 分析股票
- 每日分析
- 技术面分析
- 买入信号
- 大盘复盘

## 功能

### 1. 多市场支持
- A股（上证、深证、北交所）
- 港股
- 美股

### 2. 技术面分析

| 指标 | 说明 |
|------|------|
| MA5/10/20 | 5/10/20日均线 |
| MACD | 指数平滑异同移动平均线 |
| RSI | 相对强弱指标 |
| BIAS | 乖离率 |

### 3. 趋势判断
- 多头排列
- 空头排列
- 震荡整理

### 4. AI 决策

```python
{
    'sentiment_score': 75,        # 情绪评分
    'operation_advice': '买入',    # 操作建议
    'confidence_level': '高',       # 信心水平
    'target_price': '1550',        # 目标价
    'stop_loss': '1420'           # 止损价
}
```

## 使用

```python
from scripts.analyzer import analyze_stock

# 单只分析
result = analyze_stock('600519')  # 贵州茅台
print(result['ai_analysis']['operation_advice'])

# 批量分析
results = analyze_stock(['600362', '601318', '159892'])
```

## 配置

1. 安装依赖：
```bash
pip install akshare pandas openai
```

2. 配置 API（可选）：
```json
{
  "ai": {
    "provider": "openai",
    "api_key": "your-key",
    "model": "gpt-4"
  }
}
```

## 输出示例

```
📊 贵州茅台(600519) 技术分析

均线状态: 多头排列 ↑
MA5: 1850.0 | MA10: 1820.0 | MA20: 1800.0

MACD: 金叉 ↑
RSI: 75 (超买但未到顶)

🟢 买入信号: 75分

AI 建议:
- 操作: 买入
- 信心: 高
- 目标价: 1950
- 止损: 1780
```

---

## 协同Skills

- `akshare-cn-finance`: 数据源
- `stock-watcher`: 自选股监控
