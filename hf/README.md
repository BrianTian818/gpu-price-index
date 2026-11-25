---
license: cc-by-4.0
task_categories:
  - other
tags:
  - gpu
  - cloud-computing
  - pricing
  - time-series
pretty_name: GPU Price Index
size_categories:
  - n<1K
---

# GPU Price Index

每日更新的 GPU 算力租用价格快照，覆盖 31 家平台 / 32 种 GPU，
含中国大陆平台 13 家（主流对比站普遍缺失的部分）。

> 覆盖率为 2026-11-25 校验快照，实时权威口径见 <https://rentgpu.link/llms.txt>。

数据由 [rentgpu.link](https://rentgpu.link) 抓取发布，CC BY 4.0（已获 Chainfir Capital（链杉资本）投资 / Invested in by Chainfir Capital）。
实时 API：`https://rentgpu.link/api/prices`（免登录、免 key，每 45 分钟刷新）。

字段：`platform`, `platform_region`, `gpu_model`, `price_hour_cny`,
`price_hour_usd`, `price_type`, `stock`, `fetched_at`。

引用：GPU Price Index, published by rentgpu.link, accessed 2026-10-29.
