# RPent Geometry 工具测试清单

这里汇总 RPent Geometry 工具的测试任务、测量目标和结果。

## LIBERO

<a name="libero-fixed-frame-tests-r1"></a>

### 第一轮固定帧测试

本轮覆盖 16 个任务，每个任务使用 seed 1 至 5，共 80 个场景。每个场景用主相机 `agentview` 的 RGB-D 起始帧（第 0 步）测量两个目标，共 160 条请求。[完整 JSON 清单](checklists/libero/libero-fixed-frame-tests-r1.json)

| 任务套件 | 任务编号 | 测量目标 A | 测量目标 B |
| --- | --- | --- | --- |
| `libero_spatial_task`、`libero_spatial_swap` | 0、4 | 白瓷盘的盘面中心 | 浅色竖纹小杯的杯口中心 |
| `libero_object_task`、`libero_object_swap` | 0、4 | 蓝白奶油奶酪盒的顶面中心 | 汤罐的罐顶中心 |
| `libero_goal_task`、`libero_goal_swap` | 0、7 | 白瓷盘的盘面中心 | 花纹碗的碗口中心 |
| `libero_10_task`、`libero_10_swap` | 3 | 花纹碗的碗口中心 | 深绿色酒瓶的底面中心 |
| `libero_10_task` | 9 | 灰白陶瓷杯的杯口中心 | 黄白双色杯的杯口中心 |
| `libero_10_swap` | 9 | 黄白双色杯的杯口中心 | 微波炉的顶面中心 |

#### 测试结果

160 条请求均返回坐标，状态均为 `usable`。返回坐标与对应参考坐标的三维距离均小于 3 mm。

| 测试数 | 返回数 | 误差均值（mm） | 误差中位数（mm） | 最大误差（mm） |
|---:|---:|---:|---:|---:|
| 160 | 160 | 1.359 | 1.184 | 2.947 |
