---
name: akshare-cn-finance
description: A股/港股/美股实时行情数据Skill。通过AkShare库获取中国金融市场数据，支持A股、港股、美股、期货、基金、宏观经济指标等。适用于用户请求中国行情数据、股票价格、市场分析或金融信息。
---

# A股金融数据 (AkShare)

> 获取中国金融市场数据的 OpenClaw Skill

## 定位

通过 AkShare 库获取中国金融市场数据，包括：
- A股（上海/深圳交易所）
- 港股
- 美股
- 期货
- 基金
- 宏观经济指标

## 触发条件

用户提到：
- A股数据
- 港股行情
- 大盘分析
- 中国金融市场
- 股票价格查询
- 宏观经济数据

## 功能

### A股数据

**实时行情：**
```python
import akshare as ak
df = ak.stock_zh_a_spot_em()  # 全部A股实时
df = ak.stock_zh_a_spot()     # 个股实时
```

**历史数据：**
```python
df = ak.stock_zh_a_hist(
    symbol="000001",
    period="daily",
    start_date="20240101",
    end_date="20241231",
    adjust="qfq"
)
```

**股票列表：**
```python
df = ak.stock_info_a_code_name()
```

### 港股数据

```python
df = ak.stock_hk_spot_em()     # 实时行情
df = ak.stock_hk_hist(symbol="00700", period="daily")  # 历史
```

### 宏观经济

```python
df = ak.macro_china_gdp()     # GDP
df = ak.macro_china_cpi()     # CPI
df = ak.macro_china_pmi()     # PMI
```

## 安装

```bash
pip install akshare pandas
```

## 常用函数速查

| 功能 | 函数 |
|------|------|
| A股实时 | `stock_zh_a_spot_em()` |
| A股历史 | `stock_zh_a_hist()` |
| 港股实时 | `stock_hk_spot_em()` |
| 基金净值 | `fund_open_fund_info_em()` |
| GDP | `macro_china_gdp()` |
| CPI | `macro_china_cpi()` |

## 注意事项

1. **无缓存**：AkShare 不缓存数据，需自行实现
2. **频率限制**：注意请求频率，避免被封
3. **数据格式**：返回 pandas DataFrame

---

## 使用示例

```
用户: 查询贵州茅台今日行情
→ 调用 stock_zh_a_spot_em() → 返回实时行情

用户: 获取上证指数近一年走势
→ 调用 stock_zh_a_hist(symbol="000001") → 返回K线数据

用户: 最近GDP数据
→ 调用 macro_china_gdp() → 返回宏观数据
```

---

## 协同Skills

- `stock-daily-analysis`: 每日股票分析
- `stock-watcher`: 自选股监控
