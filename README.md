# fund-etf-hist · ETF 历史行情查询

基于 AKShare `fund_etf_hist_sina` 接口封装的 ETF 日频率历史行情数据查询工具。

## 功能

输入ETF基金代码，返回自上市以来的完整日频行情数据（OHLCV），包括：
- 日期、开盘价、最高价、最低价、收盘价
- 成交量（单位：手）

## 常用ETF代码

| 代码 | 名称 |
|------|------|
| sh510050 | 上证50ETF |
| sh510300 | 沪深300ETF |
| sh510500 | 中证500ETF |
| sh588000 | 科创50ETF |
| sz159915 | 创业板ETF |
| sz159845 | 中证1000ETF |
| sh518880 | 黄金ETF |
| sh511880 | 货币ETF |

## 使用示例

```python
import akshare as ak

# 获取上证50ETF全部历史数据
df = ak.fund_etf_hist_sina(symbol="sh510050")
print(df)
```

输出：
```
            date   open   high    low  close      volume
0     2005-02-23  0.881  0.882  0.866  0.876  1269742542
1     2005-02-24  0.876  0.876  0.868  0.876   451614223
...          ...    ...    ...    ...    ...         ...
```

## 安装

```bash
# 前提：安装 AKShare
pip install akshare

# 复制到系统Skills目录
cp -r fund-etf-hist ~/.claude/skills/
```

## 依赖

- akshare >= 1.0.0
- pandas

## 数据来源

新浪财经 http://vip.stock.finance.sina.com.cn/fund_center/index.html#jjhqetf
