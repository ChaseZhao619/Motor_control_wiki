# 无刷电机控制

无刷电机（Brushless DC Motor, BLDC）用电子换向替代电刷换向。控制器必须知道或估计转子磁场位置，再控制三相绕组电流，使定子磁场持续产生期望转矩。

## 基本结构与工作原理

BLDC 通常由永磁转子（Permanent Magnet Rotor）、三相定子绕组（Three-phase Stator Winding）和电子调速器或驱动器组成。三相逆变器（Three-phase Inverter）由六个功率开关构成，用于给 U、V、W 三相施加电压。

## 关键词汇与注释

| 中文术语 | English | 注释 |
| --- | --- | --- |
| 电子换向 | Electronic Commutation | 用功率开关按转子位置切换相电流方向。 |
| 霍尔传感器 | Hall Sensor | 检测转子磁极位置的传感器。 |
| 无感控制 | Sensorless Control | 不用位置传感器，依靠反电动势或观测器估计转子位置。 |
| 六步换相 | Six-step Commutation | 每 60 电角度切换一次导通相的控制方法。 |
| 磁场定向控制 | Field-oriented Control, FOC | 将电流分解到磁链方向和转矩方向进行矢量控制。 |

## 数学模型与变量定义

三相电压方程可写为：

$$
\mathbf{v}_{abc}=R_s\mathbf{i}_{abc}+L_s\frac{d\mathbf{i}_{abc}}{dt}+\mathbf{e}_{abc}
$$

其中 $\mathbf{v}_{abc}$ 是三相电压，$\mathbf{i}_{abc}$ 是三相电流，$R_s$ 是相电阻，$L_s$ 是相电感，$\mathbf{e}_{abc}$ 是三相反电动势。

FOC 常用 Clarke 变换（Clarke Transform）把三相量变到静止 $\alpha\beta$ 坐标：

$$
\begin{bmatrix}
i_\alpha \\
i_\beta
\end{bmatrix}
=
\frac{2}{3}
\begin{bmatrix}
1 & -\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{\sqrt{3}}{2} & -\frac{\sqrt{3}}{2}
\end{bmatrix}
\begin{bmatrix}
i_a\\
i_b\\
i_c
\end{bmatrix}
$$

再用 Park 变换（Park Transform）进入随转子旋转的 $dq$ 坐标：

$$
\begin{bmatrix}
i_d\\
i_q
\end{bmatrix}
=
\begin{bmatrix}
\cos\theta_e & \sin\theta_e\\
-\sin\theta_e & \cos\theta_e
\end{bmatrix}
\begin{bmatrix}
i_\alpha\\
i_\beta
\end{bmatrix}
$$

表贴式永磁同步电机近似满足：

$$
\tau_e=\frac{3}{2}p\psi_f i_q
$$

其中 $p$ 是极对数（Pole Pairs），$\psi_f$ 是永磁体磁链（Permanent Magnet Flux Linkage）。在 $i_d=0$ 控制下，转矩主要由 $i_q$ 决定。

## 常见控制目标

- 开环启动：在低速时用预设换相或强拖方式启动。
- 速度控制：控制换相频率、电压或 $i_q$，使转速跟随目标。
- 转矩控制：通过电流环控制 $i_q$。
- 高效率控制：使用 FOC 降低转矩脉动和电流损耗。

## 主流控制方法

六步换相按霍尔状态或反电动势过零点选择两相导通、一相悬空。它实现简单，但转矩脉动较大。

无感反电动势控制依赖关系：

$$
e \propto \omega
$$

低速时反电动势很小，因此无感 BLDC 往往需要开环启动，达到一定速度后再切入闭环估计。

FOC 的目标是把电流矢量锁定在最有效的转矩方向。典型控制律为：

$$
e_d=i_d^\*-i_d,\quad e_q=i_q^\*-i_q
$$

$$
v_d=K_{pd}e_d+K_{id}\int e_d dt
$$

$$
v_q=K_{pq}e_q+K_{iq}\int e_q dt
$$

再经过反 Park 变换和空间矢量脉宽调制（Space Vector PWM, SVPWM）生成三相逆变器占空比。

## 控制框图

```mermaid
flowchart LR
    W[速度或转矩目标] --> REF[iq 目标]
    REF --> IDQ[dq 电流 PI]
    ANG[转子电角度] --> PARK[Park/反 Park 变换]
    IDQ --> PARK
    PARK --> SVPWM[SVPWM]
    SVPWM --> INV[三相逆变器]
    INV --> M[BLDC]
    M --> S[霍尔/编码器/观测器]
    S --> ANG
```

## 必要硬件背景

BLDC 需要三相逆变器、栅极驱动器（Gate Driver）、电流采样和位置获取链路。位置可来自霍尔传感器、编码器或无感观测器。电流采样可使用低边采样、相电流采样或母线采样，采样方式会影响 FOC 的可观测性和控制精度。

## 优缺点与适用场景

优点是效率高、寿命长、功率密度高、适合高速运行。缺点是驱动复杂度高，低速无感控制困难，FOC 对采样、计算和参数敏感。适合无人机、电动工具、风扇、水泵、云台和高性能执行器。

## 常见问题与误区

- BLDC 不等于只能六步换相；高性能 BLDC 常用 FOC。
- 无感控制不是没有反馈，而是反馈来自电压、电流和模型估计。
- 电角度不等于机械角度，二者关系为 $\theta_e=p\theta_m$。

