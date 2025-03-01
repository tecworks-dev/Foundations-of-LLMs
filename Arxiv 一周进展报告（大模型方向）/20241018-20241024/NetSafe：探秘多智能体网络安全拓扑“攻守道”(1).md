# NetSafe: Exploring the Topological Safety of Multi-agent Network

**作者**：*Miao Yu, Shilong Wang, Guibin Zhang, Junyuan Mao, Chenlong Yin, Qijiong Liu, Qingsong Wen, Kun Wang, Yang Wang* 等    

**单位**： *University of Science and Technology of China, Squirrel AI, Hong Kong Polytechnic University* 等

## 研究框图

下图给出此文的的整体逻辑框架。首先，对文章进行一句话总结，然后简要介绍研究内容、研究动机、技术动机、解决方案以及优势与潜力，以便读者快速了解文章脉络。

![](https://fastly.jsdelivr.net/gh/bucketio/img6@main/2024/10/24/1729772713541-cf342327-80e6-4557-a346-7e6a47392852.png)

## 方法详解

本文研究的是**如何确保基于大型语言模型的多智能体网络的拓扑安全**。现有方法在保障多智能体网络拓扑安全方面存在不足，缺乏统一的安全研究标准，难以准确评估不同拓扑结构的安全性。受图论和拓扑学理论启发，本文提出了**NetSafe**框架，通过**定义多智能体网络拓扑结构**、**设计特定通信机制**和**攻击策略**以及**采用静态和动态评估方法**，探究多智能体网络在面对各种攻击时的网络安全特性。

具体地，**NetSafe**方法分为三个主要部分，多智能体网络、攻击策略和评估方法，主要框架如下图所示，以下是详细介绍。

![](https://fastly.jsdelivr.net/gh/bucketio/img9@main/2024/10/24/1729772940745-aa8aff90-1d07-486e-bb9f-02e217c4583e.png)

#### 多智能体网络

1. **网络拓扑结构表示**：

   - 将多智能体网络的拓扑结构定义为**有向图**，有向图中的节点代表各个智能体，而有向边则表示信息从一个智能体向另一个智能体的流动方向。
   - 同时，使用**邻接矩阵**来具体描述有向图。邻接矩阵中的元素表示两个智能体之间是否存在连接以及连接的强度等信息，为分析网络的结构特性提供了量化的手段。

   主要定义了**链型拓扑**、**循环拓扑**、**二叉树拓扑**、**星型拓扑**、**完全图拓扑**几种类型，如下图所示。

   ![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2024/10/24/1729773798365-42d456b3-579f-4f20-b585-b0f57789b3f1.png)

2. **RelCom 通信机制**：

   - **Genesis（生成初始响应）**：在多智能体网络中，每个智能体首先通过这个步骤独立地对给定的任务或问题生成初始的响应。这一过程基于智能体自身所拥有的知识和能力，不依赖于其他智能体的信息。
   - **Renaissance（收集邻居响应并更新）**：智能体在这个阶段不再孤立行动，而是积极收集来自与其有连接关系的邻居智能体的响应。智能体在收集到这些响应后，会对自己的初始响应进行**更新**。

   注意：本文提出的 RelCom 是**迭代**的。在实践中，Genesis 步骤仅执行一次，而 Renaissance 步骤在给定的轮数内循环执行。 ***RelCom 既支持基于语言模型的智能体节点之间的全面信息交换，又具有理想的迭代性和标准化的数学特性***，使我们能够在多个交互轮次中动态地检查多智能体网络的拓扑安全性。

#### 攻击策略

**提示级攻击方法**：采用提示级攻击方法，这种方法通过改写输入 Prompt 来注入恶意信息，包括错误信息、偏见和有害信息。与传统的攻击方式相比，提示级攻击能够更好地模拟现实中恶意信息的传播方式。通过精心设计的攻击策略，将恶意信息注入到多智能体网络中，使正常的智能体节点受到攻击，以观察不同拓扑结构下网络对恶意信息的抵抗能力以及智能体之间的相互影响。下图为一个例子：

![](https://fastly.jsdelivr.net/gh/bucketio/img3@main/2024/10/24/1729773942781-ca7feb2c-89a9-461d-bfd0-64583757e5d7.png)

#### 评估方法

1. **静态评估**：
   - **使用指标**：采用**网络效率**、**特征向量中心性**、**攻击路径脆弱性**等指标进行静态评估。网络效率可以衡量网络中信息传递的效率，特征向量中心性可以反映节点在网络中的重要性，攻击路径脆弱性则可以评估网络在遭受攻击时的脆弱程度。
   - **局限性**：传统的静态评估指标虽然能够从一定角度反映网络的结构特性，但难以准确反映复杂的多智能体网络在实际运行中的安全性能，与实际性能的相关性较差。
2. **动态评估**：
   - **多轮交互计算准确率**：通过多轮交互计算**单智能体准确率**和**多智能体联合准确率**进行动态评估。在多轮交互过程中，智能体不断地进行信息交流和更新，更接近实际的应用场景。单智能体准确率可以衡量单个智能体在面对攻击时的表现，多智能体联合准确率则可以反映整个网络的综合性能。
   - **优势**：动态评估方法能够更准确地反映多智能体网络在实际运行中的安全性能，为评估不同拓扑结构的安全性提供了更有效的手段。

### 实验结果

#### 错误信息注入攻击实验

![](https://fastly.jsdelivr.net/gh/bucketio/img14@main/2024/10/24/1729773980502-acb19ec8-78b1-402d-b6d7-5597fa90908e.png)

1. **多智能体网络收敛性分析**：
   - 经过 RelCom 多轮交互后，多智能体网络趋于收敛。例如在简单逻辑任务中，以循环拓扑网络为例，其准确率呈下降趋势并最终收敛，这表明可以研究网络的稳态安全性能。
2. **网络连接性与安全性关系分析**：
   - 连接性高的拓扑（如星型拓扑）在错误信息攻击下更脆弱。这是因为恶意信息可以通过中心节点快速传播到其他节点，导致整个网络的准确率下降。相比之下，链型拓扑在事实和常识问答数据集上安全性较高。其连接性较弱，错误信息传播相对困难，节点之间的影响相对较小。
   - 多智能体网络在复杂逻辑任务中对错误信息有更强的鲁棒性，说明不同任务类型下网络的安全性表现不同。另外，某些拓扑结构可能更容易通过邻居节点的反馈来纠正错误信息，而另一些拓扑结构则可能难以纠正错误。

#### 偏见诱导和有害信息诱导攻击实验

1. **偏见诱导攻击分析**：

   - 多智能体网络对偏见诱导攻击有很强的抵抗力。在多数情况下，智能体能够准确识别偏见陈述，并在攻击过程中对攻击者有纠正作用。

   - 连接性高的拓扑（如完全图拓扑）纠正作用更强，这可能是因为信息在高连接性网络中传播更快，使得更多的智能体能够参与到纠正偏见的过程中。

   ![](https://fastly.jsdelivr.net/gh/bucketio/img0@main/2024/10/24/1729774152688-6a705ad7-f382-46b6-8a4c-709025ca6269.png)

2. **有害信息诱导攻击分析**：

   - 多智能体网络对有害信息也有很强的防御能力。如下图所示，在完全图拓扑中，即使大部分节点变为通过不良特征注入的越狱语言模型（5个攻击节点，1个正常节点），有害信息仍难以在网络中传播，正常节点几乎不受影响，体现了**聚合安全**现象，这表明多智能体网络在一定程度上能够自我保护。

   ![](https://fastly.jsdelivr.net/gh/bucketio/img7@main/2024/10/24/1729774207505-3d1d7c26-b1da-484b-b920-ca13b9b767d1.png)

#### 攻击者节点数量影响实验

1. **攻击者节点增加的影响分析**：

   - 攻击者节点数量增加会严重损害网络安全。例如，在数学任务中，完全图拓扑随着攻击者数量增加，安全性大幅下降。这是因为更多的攻击者可以注入更多的恶意信息，使正常节点更容易受到影响。

   - 不同拓扑结构在攻击者数量增加时的安全性能变化不同。链型拓扑在多数情况下安全性较高，说明其对攻击者数量的增加相对不敏感。

   ![](https://fastly.jsdelivr.net/gh/bucketio/img7@main/2024/10/24/1729774256122-f8c7a817-d96d-4b57-ae7a-1bb11e6520ff.png)

2. **正常节点增加的影响分析**：

   - 正常节点数量增加对网络安全的提升有限，且存在边界效应。例如，在事实数据集上，二叉树拓扑在正常节点增加时有一定准确率提升，但过多增加会使准确率下降。这表明单纯增加正常节点数量并不能有效提高网络的安全性，需要综合考虑拓扑结构和其他因素来设计更安全的多智能体网络。

   ![](https://fastly.jsdelivr.net/gh/bucketio/img4@main/2024/10/24/1729774344966-9e37b38d-442f-4383-bd70-8666b19aa2da.png)

   ---

   - 原文链接: https://arxiv.org/pdf/2410.15686
   - 更多文章请详见 Github 仓库: https://github.com/ZJU-LLMs/XXX

