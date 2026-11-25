# eucli-pueue 开发空间适配说明

本目录为 `eucli-pueue`（基于上游 `Nukesor/pueue`，MIT / Apache-2.0）接入 `eucli-cf`（`contract = 3`）的轻量适配层。

- 构建产物与 Cargo target 均重定向至当前分支运行区，不污染工作树；
- `start` 按注入的 `EUCLI_CF_PORT_BASE`、`EUCLI_CF_DATA_ROOT` 与 `EUCLI_CF_INSTANCE_SUFFIX` 生成隔离的 `pueue.yml` 并拉起 `pueued`；
- `test` 先对运行中正式实例执行 `pueue add` / `status` / `clean` 队列冒烟，再运行 `pueue-lib` 单元测试。
