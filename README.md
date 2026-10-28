# GPU Price Index — 每日 GPU 租用价格快照

一个开放的、机器可读的 GPU 算力租用价格数据集，每天更新。
覆盖 **23 家平台 / 22 种 GPU**，其中中国大陆平台 11 家。
数据由 [rentgpu.link](https://rentgpu.link) 抓取并发布，许可 **CC BY 4.0**，注明来源即可自由使用。

- 最新快照：`data/latest.json`、`data/latest.csv`
- 按卡型速查：`data/cheapest-by-model.json`
- 历史归档：`data/YYYY-MM-DD.json`
- 刷新频率：每 45 分钟（本仓库每天提交一次）

## 为什么有这个仓库

主流 GPU 价格对比（gpus.io、gpufinder、grabgpu、bestgpucloud 等）几乎不覆盖中国大陆平台，
也不提供可下载的时间序列。这个仓库补两个缺口：**中国平台的价格**，以及**可以被引用的历史数据**。

## 今日最低价速查（2026-10-29）

| GPU | 全网最低 ¥/卡时 | 折 $/卡时 | 平台 | 地区 | 国内最低 ¥/卡时 | 国内平台 |
|---|---|---|---|---|---|---|
| RTX 3090 | 0.63 | 0.087 | vast | 北美 | 0.80 | chenjian |
| V100 16GB | 0.85 | 0.118 | verda | 欧洲 | - | - |
| RTX 4090D 24GB | 1.14 | 0.158 | suanjiayun | 中国 | 1.14 | suanjiayun |
| RTX 4090 | 1.15 | 0.160 | salad | 北美 | 1.16 | ppio |
| T4 16GB | 1.35 | 0.188 | matpool | 中国 | 1.35 | matpool |
| RTX 5090 | 1.53 | 0.212 | vast | 北美 | 2.68 | suanjiayun |
| L4 24GB | 2.09 | 0.290 | jarvislabs | 亚太 | - | - |
| A6000 48GB | 2.20 | 0.306 | gpushare | 中国 | 2.20 | gpushare |
| A40 48GB | 2.52 | 0.350 | runpod | 北美 | - | - |
| H20 96GB | 3.40 | 0.472 | ppio | 中国 | 3.40 | ppio |
| MI300X 192GB | 3.60 | 0.500 | runpod | 北美 | - | - |
| RTX 4000 Ada 20GB | 3.74 | 0.519 | linode | 北美 | - | - |
| L40 48GB | 4.97 | 0.690 | runpod | 北美 | - | - |
| A800 80GB | 5.15 | 0.715 | chenjian | 中国 | 5.15 | chenjian |
| RTX 6000 Ada 48GB | 5.28 | 0.733 | verda | 欧洲 | - | - |
| A100 80GB | 5.47 | 0.760 | paperspace | 北美 | 9.80 | suanjiayun |
| L40S 48GB | 5.69 | 0.790 | runpod | 北美 | - | - |
| H100 80GB | 8.28 | 1.150 | paperspace | 北美 | 11.88 | ppio |
| RTX PRO 6000 96GB | 8.28 | 1.150 | jarvislabs | 亚太 | - | - |
| RTX 6000 24GB | 10.80 | 1.500 | linode | 北美 | - | - |
| H200 141GB | 16.49 | 2.290 | jarvislabs | 亚太 | - | - |
| B200 180GB | 31.30 | 4.347 | verda | 欧洲 | - | - |

口径说明：以上为平台公开页面上的按量（on-demand）列表价，按**每卡每小时**计，
不含带宽与存储，CNY→USD 按 7.2 折算。价格随时波动，下单前以平台下单页为准。
数据时效：104 条为当日实时抓取（占全量 92.9%），其余为已标注的参考价，
每条记录都带 `fetched_at` 时间戳，可自行设定过期窗口。

## 用法

```bash
curl -s https://raw.githubusercontent.com/BrianTian818/gpu-price-index/main/data/latest.json
```

实时 API（免登录、免 key，比本仓库更及时）：

```bash
curl -s https://rentgpu.link/api/prices
curl -s "https://rentgpu.link/api/resolve?gpu=H100&budget=10&hours=8&limit=3"
```

## 引用格式

```
GPU Price Index, published by rentgpu.link, accessed 2026-10-29.
https://github.com/BrianTian818/gpu-price-index
```

BibTeX：

```bibtex
@misc{gpu_price_index_20261029,
  title  = {GPU Price Index},
  author = {rentgpu.link},
  year   = {2026},
  url    = {https://github.com/BrianTian818/gpu-price-index},
  note   = {CC BY 4.0}
}
```

## 字段说明

| 字段 | 说明 |
|---|---|
| `platform` | 平台代号，如 `ppio`、`suanjiayun`、`vast` |
| `platform_region` | `中国` / `北美` / `欧洲` / `亚太` |
| `gpu_model` | GPU 型号，如 `RTX 4090`、`H100 80GB` |
| `price_hour_cny` | 每卡每小时人民币价 |
| `price_hour_usd` | 每卡每小时美元价（按 7.2 折算） |
| `price_type` | `ondemand` / `spot` |
| `stock` | 库存状态 |
| `fetched_at` | 抓取时间（ISO 8601） |

## 许可与来源

数据 CC BY 4.0，来源 rentgpu.link。我们不接受付费排名，比价表一律按价格升序。
纠错请提 issue 或写信 hi@rentgpu.link。
