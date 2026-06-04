# 参考资料与检索关键词

本页列出继续学习电机控制时常用的资料类型和检索关键词。这里不绑定具体开发板、芯片 SDK 或代码库。

## 教材方向

- 电机学（Electric Machinery）：用于理解电机结构、反电动势、转矩、电磁转换和等效模型。
- 自动控制原理（Automatic Control）：用于理解反馈、稳定性、带宽、PID 和频域分析。
- 电力电子技术（Power Electronics）：用于理解 H 桥、三相逆变器、PWM、MOSFET 和驱动保护。
- 机器人学或机电控制（Mechatronics）：用于理解执行器、传感器、级联控制和运动控制。

## 厂商应用笔记方向

- BLDC 六步换相（BLDC Six-step Commutation）
- BLDC 无感控制（Sensorless BLDC Control）
- 反电动势过零检测（Back-EMF Zero Crossing Detection）
- 磁场定向控制（Field-oriented Control, FOC）
- 空间矢量脉宽调制（Space Vector PWM, SVPWM）
- 步进电机恒流斩波驱动（Stepper Chopper Current Drive）
- 直流电机 H 桥驱动与电流限制（DC Motor H-bridge Current Limit）

## 在线参考

- [FOC 相关图文说明（知乎）](https://zhuanlan.zhihu.com/p/147659820)：可作为理解 FOC 坐标变换、转矩电流和控制流程的补充阅读。本文档不复制其中图片，使用重新绘制的 Mermaid 图说明信号流。

## 数据手册阅读重点

阅读电机或驱动芯片数据手册时，优先关注：

- 额定电压、额定电流、峰值电流和堵转电流。
- 相电阻、相电感、反电动势常数和转矩常数。
- 霍尔排列、编码器分辨率、极对数和最大机械转速。
- 驱动器最大母线电压、连续电流、峰值电流、PWM 频率、保护功能。
- 散热条件、工作制、温升和安全余量。

## 推荐检索关键词

| 主题 | 中文关键词 | English Keywords |
| --- | --- | --- |
| 直流电机建模 | 有刷直流电机 数学模型 | brushed DC motor modeling |
| 速度控制 | 直流电机 PI 速度环 | DC motor PI speed control |
| 步进电机 | 步进电机 细分 失步 | stepper motor microstepping lost step |
| BLDC 六步 | 无刷电机 六步换相 霍尔 | BLDC six-step commutation hall sensors |
| BLDC 无感 | 反电动势 过零检测 无感控制 | sensorless BLDC back-EMF zero crossing |
| FOC | 磁场定向控制 dq 坐标 | field-oriented control dq transform |
| SVPWM | 空间矢量 PWM 三相逆变器 | space vector PWM three-phase inverter |
| 电流采样 | 低边采样 相电流采样 | low-side current sensing phase current sensing |

## 导航

[上一页：术语表](glossary.md) | [返回目录](../README.md)
