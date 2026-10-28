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

每日更新的 GPU 算力租用价格快照，覆盖 23 家平台 / 22 种 GPU，
含中国大陆平台 11 家（主流对比站普遍缺失的部分）。

数据由 [rentgpu.link](https://rentgpu.link) 抓取发布，CC BY 4.0。
实时 API：`https://rentgpu.link/api/prices`（免登录、免 key）。

字段：`platform`, `platform_region`, `gpu_model`, `price_hour_cny`,
`price_hour_usd`, `price_type`, `stock`, `fetched_at`。

引用：GPU Price Index, published by rentgpu.link, accessed 2026-10-29.
