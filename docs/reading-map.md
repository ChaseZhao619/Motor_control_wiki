# 阅读路线

本页按学习目标组织 wiki 的阅读顺序。若只想快速建立整体认知，先走“入门理解”；若正在研究无刷电机控制，直接走“BLDC 深入”。

## 入门理解

1. [电机控制总览](overview.md)：理解开环、闭环和控制层级。
2. [电机类型对比](comparison.md)：建立不同电机的选型直觉。
3. [必要硬件背景](hardware-background.md)：理解驱动器、采样和传感器。
4. [术语表](glossary.md)：查阅中英文术语、缩写和符号。

## 理论推导

1. [控制理论基础](control-theory.md)：先理解 PID、级联控制、带宽和饱和。
2. [TT 电机控制](dc-tt-motor.md)：从有刷直流电机模型入手。
3. [直流减速电机控制](dc-geared-motor.md)：理解齿轮箱和等效惯量。
4. [步进电机控制](stepper-motor.md)：理解开环位置控制和失步机理。
5. [无刷电机控制](bldc-motor.md)：进入三相模型、换相和 FOC。

## 选型应用

1. [电机类型对比](comparison.md)：先按成本、精度、效率和复杂度筛选。
2. [必要硬件背景](hardware-background.md)：确认驱动器、电流采样和保护要求。
3. 对应阅读电机专题页，重点关注“优缺点与适用场景”和“常见问题与误区”。

## BLDC 深入

1. [必要硬件背景](hardware-background.md)：理解三相逆变器、电流采样和位置传感。
2. [无刷电机控制](bldc-motor.md)：阅读六步换相、无感控制和 FOC。
3. [控制理论基础](control-theory.md)：补齐电流环、速度环、采样周期和抗积分饱和。
4. [参考资料与检索关键词](references.md)：继续查找厂商应用笔记和教材章节。

## 导航

[上一页：电机控制总览](overview.md) | [返回目录](../README.md) | [下一页：TT 电机控制](dc-tt-motor.md)
