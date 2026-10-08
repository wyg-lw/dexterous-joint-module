# dexterous-joint-module
This is a repository that contains multiple open-source projects. It is used to document my daily learning process of the dexterous hand and also for sharing.
# dexterous-joint-module 低成本灵巧手关节模组

用 <300 元实现一个可通过 CAN 总线控制的 FOC 关节模组原型，
固件、协议与调参数据全部开源。

## 目标与验收标准
- [x] M0：项目建立，位置/速度环初步调通
- [ ] M1：FreeRTOS 实时架构（抖动 < xx μs）
- [ ] M2：CAN 双节点互通（协议见 docs/02）
- [ ] M3：电流环带宽 ≥ 500 Hz（数据见 docs/03）
- [ ] M4：STM32G4 + ESP32 异构总线演示

## 硬件
| 器件 | 用途 | 成本 |
|---|---|---|
| B-G431B-ESC1 (STM32G431) | 关节控制器，FOC 三环 | ¥200 |
| ESP32-S3 | 协调器，CAN 上层节点 | ¥25（已有）|
| 云台电机 + AS5600 | 被控对象/位置反馈 | 已有 |
| TJA1050 / SN65HVD230 | CAN 收发器 | ¥5 |

## 架构
（一张框图：上位机 → CAN 总线 → [协调器 ESP32-S3] / [关节控制器 G431] → 电机）

## 结果
- 电流环波形：results/current_loop_bandwidth.png
- 演示视频：assets/demo.mp4

## 参考
SimpleFOC / ST MCSDK / ESP-IDF TWAI 文档
