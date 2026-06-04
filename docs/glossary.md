# 术语表

本页汇总 wiki 中的关键中文术语、英文名、常用缩写、注释和相关章节。首次阅读时建议只查需要的词，不必一次读完。

## 关键术语

| 中文术语 | English | 缩写 | 注释 | 相关章节 |
| --- | --- | --- | --- | --- |
| 电机控制 | Motor Control | - | 通过电压、电流、磁场或换相时序控制电机输出。 | [总览](overview.md) |
| 开环控制 | Open-loop Control | - | 不测量输出结果，按预设命令驱动。 | [总览](overview.md) |
| 闭环控制 | Closed-loop Control | - | 测量输出并根据误差修正控制量。 | [总览](overview.md) |
| 脉宽调制 | Pulse Width Modulation | PWM | 用开关波形的占空比调节平均电压。 | [TT 电机](dc-tt-motor.md) |
| 占空比 | Duty Cycle | - | 一个 PWM 周期内高电平时间占比。 | [总览](overview.md) |
| 反电动势 | Back Electromotive Force | Back-EMF | 电机转动时绕组产生的感应电压。 | [TT 电机](dc-tt-motor.md), [BLDC](bldc-motor.md) |
| 转矩常数 | Torque Constant | - | 电流与电磁转矩之间的比例系数。 | [总览](overview.md) |
| 堵转电流 | Stall Current | - | 电机被卡住且反电动势为零时的最大电流。 | [TT 电机](dc-tt-motor.md) |
| 电流环 | Current Loop | - | 控制绕组电流的内环，直接影响转矩。 | [控制理论](control-theory.md) |
| 速度环 | Speed Loop | - | 控制角速度的闭环。 | [控制理论](control-theory.md) |
| 位置环 | Position Loop | - | 控制角度或位移的闭环。 | [控制理论](control-theory.md) |
| 级联控制 | Cascade Control | - | 外环生成内环目标的多环控制结构。 | [控制理论](control-theory.md) |
| 采样周期 | Sampling Period | `T_s` | 离散控制器两次计算之间的时间间隔。 | [控制理论](control-theory.md) |
| 有刷直流电机 | Brushed DC Motor | BDC | 依靠电刷和换向器进行机械换向。 | [TT 电机](dc-tt-motor.md) |
| 直流减速电机 | DC Geared Motor | - | 直流电机加齿轮箱形成的执行器。 | [直流减速电机](dc-geared-motor.md) |
| 减速比 | Gear Ratio | - | 电机轴速度与输出轴速度的比例。 | [直流减速电机](dc-geared-motor.md) |
| 等效惯量 | Reflected Inertia | - | 通过传动比折算到同一轴侧的惯量。 | [直流减速电机](dc-geared-motor.md) |
| 齿隙 | Backlash | - | 齿轮啮合间隙导致的反向空程。 | [TT 电机](dc-tt-motor.md) |
| 步进电机 | Stepper Motor | - | 通过脉冲驱动产生离散角位移的电机。 | [步进电机](stepper-motor.md) |
| 细分 | Microstepping | - | 用相电流比例把整步划分为更小指令位置。 | [步进电机](stepper-motor.md) |
| 斩波驱动 | Chopper Drive | - | 用开关方式调节绕组电压，使相电流跟随目标值。 | [步进电机](stepper-motor.md) |
| 保持转矩 | Holding Torque | - | 静止通电时可抵抗的最大外部转矩。 | [步进电机](stepper-motor.md) |
| 失步 | Lost Step | - | 指令步数与实际转子位置不再一致。 | [步进电机](stepper-motor.md) |
| 无刷电机 | Brushless DC Motor | BLDC | 用电子换向替代电刷换向的电机。 | [BLDC](bldc-motor.md) |
| 电子换向 | Electronic Commutation | - | 根据转子位置切换绕组通电状态。 | [BLDC](bldc-motor.md) |
| 六步换相 | Six-step Commutation | - | 每 60 电角度切换一次导通相。 | [BLDC](bldc-motor.md) |
| 电角度 | Electrical Angle | - | 以电磁周期计量的角度，等于机械角度乘以极对数。 | [BLDC](bldc-motor.md) |
| 机械角度 | Mechanical Angle | - | 转子实际机械旋转角度。 | [BLDC](bldc-motor.md) |
| 极对数 | Pole Pairs | `p` | 电机中成对磁极的数量，决定机械角度与电角度比例。 | [BLDC](bldc-motor.md) |
| Clarke 变换 | Clarke Transform | - | 把三相静止坐标量变换到两相静止 `αβ` 坐标。 | [BLDC](bldc-motor.md) |
| Park 变换 | Park Transform | - | 把静止 `αβ` 坐标量变换到旋转 `dq` 坐标。 | [BLDC](bldc-motor.md) |
| dq 坐标系 | Direct-quadrature Reference Frame | dq | 随转子磁场旋转的坐标系，用于分解磁链和转矩电流。 | [BLDC](bldc-motor.md) |
| 磁场定向控制 | Field-oriented Control | FOC | 在旋转坐标系中独立控制励磁和转矩电流。 | [BLDC](bldc-motor.md) |
| 空间矢量脉宽调制 | Space Vector PWM | SVPWM | 用逆变器开关状态合成目标电压矢量。 | [BLDC](bldc-motor.md) |
| 反电动势过零 | Back-EMF Zero Crossing | ZC | 悬空相反电动势经过中性点电压的时刻，可用于无感换相。 | [BLDC](bldc-motor.md) |
| 霍尔传感器 | Hall Sensor | - | 利用霍尔效应检测转子磁极位置。 | [硬件背景](hardware-background.md) |
| 编码器 | Encoder | - | 测量角度、位置或速度的传感器。 | [硬件背景](hardware-background.md) |
| H 桥 | H-Bridge | - | 用四个开关控制直流电机正反转。 | [硬件背景](hardware-background.md) |
| 三相逆变器 | Three-phase Inverter | - | 用六个功率开关驱动三相电机。 | [硬件背景](hardware-background.md) |
| 栅极驱动器 | Gate Driver | - | 控制 MOSFET 栅极快速充放电的驱动电路。 | [硬件背景](hardware-background.md) |
| 死区时间 | Dead Time | - | 同一桥臂上下管都关断的一小段时间，用于避免直通。 | [硬件背景](hardware-background.md) |
| 抗积分饱和 | Anti-windup | - | 防止控制输出限幅后积分项继续累积。 | [控制理论](control-theory.md) |

## 常用符号

| 符号 | 含义 | 单位 |
| --- | --- | --- |
| `u, v` | 电压 | V |
| `i` | 电流 | A |
| `R` | 电阻 | ohm |
| `L` | 电感 | H |
| `ω` | 角速度 | rad/s |
| `θ` | 角位置 | rad |
| `τ` | 转矩 | N·m |
| `J` | 转动惯量 | kg·m² |
| `B` | 粘性阻尼系数 | N·m·s/rad |
| `K_t` | 转矩常数 | N·m/A |
| `K_e` | 反电动势常数 | V·s/rad |
| `D` | PWM 占空比 | 1 或 % |
| `T_s` | 采样周期 | s |
| `p` | 极对数 | 1 |
| `N` | 减速比 | 1 |

## 导航

[上一页：电机类型对比](comparison.md) | [返回目录](../README.md) | [下一页：参考资料与检索关键词](references.md)
