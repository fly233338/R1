### Vision-R1: Evolving Human-Free Alignment in Large Vision-Language Models via Vision-Guided Reinforcement Learning 2025/03/23

> 作者提出了Vision-R1，一种新颖的视觉定位 R1-like强化学习算法，用于LVLMs，其通过视觉反馈提供奖励以促进对任务的理解超越SFT。作者提出了一种有效的渐进式规则细化策略，该策略通过在训练过程中动态调整奖励标准来确保持续提升。在领域内还是领域外场景下，均实现了卓越的性能提升，Qwen2.5-VL模型甚至达到了50%的改进，同时保持了良好的泛化能力。作者在多个**目标定位任务**和数据集上进行了实验，以验证Vision-R1的有效性

>输出格式: 每个预测实例包含坐标、类别标签和交并比（IoU）

**奖励设计**
1. DualFormatReward: 坐标约束和json格式
2. Recall: 为每个预测的完成结果设计了一个基于召回的奖励。当匹配预测实例的IoU超过预定义的阈值时，它被视为有效预测。召回奖励是所有真实目标中有效预测的比例。
3. Percision: 为了直接激励模型预测高质量的边界框，作者将精确奖励定义为所有有效预测的平均交并比（IoU）
**奖励为三者之和**

