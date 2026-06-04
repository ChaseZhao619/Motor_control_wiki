# Motor Control Wiki

这是一个关于常见电机控制方法的中文 wiki。内容面向希望系统理解电机控制理论的读者，重点解释模型、控制目标、控制策略、公式推导、控制框图和必要硬件背景，不提供具体代码级控制库。

关键词汇采用“中文术语（English Term, Abbreviation）”格式，并在首次出现处给出简短注释。例如：反电动势（Back Electromotive Force, Back-EMF）指电机转动时绕组中感应出的、方向与外加电压相反的电压。

## 阅读路径

1. 先阅读 [电机控制总览](docs/overview.md)，理解开环、闭环、电流环、速度环和位置环。
2. 再按电机类型阅读专题：
   - [TT 电机控制](docs/dc-tt-motor.md)
   - [直流减速电机控制](docs/dc-geared-motor.md)
   - [步进电机控制](docs/stepper-motor.md)
   - [无刷电机控制](docs/bldc-motor.md)
3. 需要统一理论框架时阅读 [控制理论基础](docs/control-theory.md)。
4. 遇到驱动器、传感器和采样概念时阅读 [必要硬件背景](docs/hardware-background.md)。
5. 选型或比较时阅读 [电机类型对比](docs/comparison.md)。
6. 查术语、英文名和符号时阅读 [术语表](docs/glossary.md)。

## 内容范围

- 覆盖：TT 电机、直流减速电机、步进电机、无刷电机。
- 覆盖：数学模型、控制目标、典型控制方法、必要硬件背景、优缺点和常见误区。
- 不覆盖：平台绑定 API、具体代码库、完整 PCB 设计、量产级安规和认证。

## 文档目录

| 文档 | 内容 |
| --- | --- |
| [overview.md](docs/overview.md) | 电机控制总览与控制层级 |
| [dc-tt-motor.md](docs/dc-tt-motor.md) | TT 电机的 PWM 调速与闭环控制 |
| [dc-geared-motor.md](docs/dc-geared-motor.md) | 直流减速电机模型、齿轮箱影响与控制 |
| [stepper-motor.md](docs/stepper-motor.md) | 步进电机开环、细分和加减速控制 |
| [bldc-motor.md](docs/bldc-motor.md) | 无刷电机六步换相、无感控制和 FOC |
| [control-theory.md](docs/control-theory.md) | PID、级联控制和稳定性 |
| [hardware-background.md](docs/hardware-background.md) | H 桥、逆变器、采样、编码器和保护 |
| [comparison.md](docs/comparison.md) | 电机类型对比和适用场景 |
| [glossary.md](docs/glossary.md) | 中英术语、缩写、符号和注释 |

