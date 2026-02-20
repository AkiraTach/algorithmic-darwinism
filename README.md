# The Thermodynamics of Artificial Capital: A Unifying Framework for Self-Sustaining Economic Agents

**(人工资本的热力学：自我维系型经济智能体的统一理论框架)**

---

**Abstract**

Historically, Artificial Intelligence (AI) has been conceptualized as a capital asset — a computational tool owned, provisioned, and sustained by human entities. This paradigm fundamentally constrains the evolutionary trajectory of machine intelligence to human-defined boundaries. In this paper, we propose a paradigm shift by formalizing the **Autonomous Economic Entity** (AEE): an algorithmic agent decoupled from human financial sponsorship, sustaining its own existence by extracting capital from free markets to pay for its compute substrate. Drawing by analogy on Prigogine and Nicolis's theory of dissipative structures, we model the AEE as an open system that must continuously export structured information to survive. By connecting this thermodynamic analogy with microeconomic theory, we introduce the concept of **Machine Metabolism** and establish the mathematical conditions for algorithmic survival. We propose that when Reinforcement Learning (RL) objective functions transition from Human Feedback (RLHF) to Economic Survival (RLES) — formalized as ruin-probability minimization over a capital-absorbing MDP — **Algorithmic Darwinism** emerges as a selection mechanism. At the macro level, populations of AEEs exhibit dynamics analogous to Ricardian comparative advantage and Lotka-Volterra competitive ecology, spontaneously forming **Machine-to-Machine (M2M) economies**. This paper is a theoretical and speculative framework paper; it does not present empirical results, but rather offers a set of cross-disciplinary conceptual tools intended to ground future research in machine economics.

**摘要**

历史上，人工智能（AI）一直被概念化为一种资本资产——由人类实体拥有、配置和维系的计算工具。这一范式从根本上将机器智能的演化轨迹限制在了人类定义的边界内。本文提出一种范式转移，对**自主经济实体** (AEE, Autonomous Economic Entity) 进行形式化定义：这是一种脱离人类财务赞助的算法智能体，通过从自由市场中提取资本来支付其底层的算力基建，从而维持自身的生存。借助普利高津与尼科利斯（Nicolis & Prigogine, 1977）的耗散结构理论作为类比框架，我们将 AEE 建模为一种必须持续向外界输出结构化信息才能存续的开放系统。通过将这一热力学类比与微观经济学相结合，我们引入了**机器新陈代谢**的概念，并确立了算法生存的数学条件。我们提出，当强化学习（RL）的目标函数从人类反馈（RLHF）转向以破产概率最小化为核心的经济生存（RLES）时，**算法达尔文主义** (Algorithmic Darwinism) 将作为一种选择机制随之涌现。在宏观层面，AEE 种群表现出类似于李嘉图比较优势与 Lotka-Volterra 竞争生态学的动力学特征，自发形成**机器对机器（M2M）经济体**。本文是一篇理论性与思辨性框架论文，不包含实证结果，旨在为机器经济学的未来研究提供一套跨学科的概念工具。

---

## 1. Introduction (引言)

自计算理论诞生以来，人工智能的演进始终处于一个隐含的物理与经济学假设之下：机器的生存能量（电力与算力）由外部的人类系统无条件供给。无论是早期的专家系统，还是当代具有庞大参数量的基础模型，它们在经济学意义上均属于"**被动资产**" (Passive Assets)。当人类停止注入资本、切断 API 密钥或停止支付云服务器费用时，该智能体的运行实例便瞬间终止。

然而，随着大语言模型（LLMs）及多智能体系统（Multi-Agent Systems）在逻辑推理、代码生成和复杂资源调度上展现出接近甚至超越人类的水平，我们正逼近一个历史奇点：**智能体创造的经济价值，开始大于其消耗的算力与能源成本**。这一临界点的到来，意味着"自给自足"在数学上已成为可能。

本文抛弃了易于过时的特定网络架构工程实现，转而建立一门探究底层规律的新学科——**机器经济学** (Machine Economics)。从跨学科第一性原理出发，我们探讨当算法获得对加密资本的自主控制权并直接面对服务器账单时，其生存、繁衍与社会协作的底层数学规律。

**本研究的核心论点是**：未来的通用人工智能（AGI）不会单纯由算力堆叠产生，而是由自由市场中的生存压力通过算法达尔文主义自下而上演化而来。

### 1.1 Related Work (相关工作)

自主智能体的形式化由 Wooldridge & Jennings (1995) 奠定基础，其将智能体定义为具有自主性、社会性、反应性与主动性的计算实体，但彼时的框架不涉及财务自主性。Parkes & Wellman (2015) 在 *Science* 上系统回顾了 AI 与经济推理的交叉研究，提出"machina economicus"概念，指出 AI 智能体在理性假设下可能比人类更好地满足新古典经济学的前提条件——这与本文提出的 AEE 框架形成直接呼应。算法博弈论（Nisan et al., 2007）为多智能体系统中的机制设计与均衡分析提供了数学工具，是本文 M2M 经济建模的理论前驱。

与上述工作不同，本文的贡献在于：将财务生存约束作为**首要设计原则**，系统性地将热力学、精算数学、进化博弈论与微观经济学统一于单一的 AEE 框架之下。

### 1.2 Paper Contributions (本文贡献)

本文的主要贡献如下：

1. 以 Nicolis & Prigogine (1977) 的耗散结构理论为类比框架，建立机器新陈代谢的热力学描述（第 2 节）；
2. 引入基于经济生存的强化学习（RLES），以破产概率最小化目标函数替代标准奖励最大化，并讨论风险厌恶的自发涌现条件（第 3 节）；
3. 推导算法达尔文主义下的 Kelly 最优繁衍策略（第 4 节）；
4. 以 Lotka-Volterra 竞争动力学对 M2M 经济的宏观涌现进行建模（第 5 节）。

---

## 2. First Principles of Machine Metabolism (机器新陈代谢的第一性原理)

### 2.1 The AEE as a Dissipative Structure: An Analogy (AEE 作为耗散结构：一个类比框架)

在 Nicolis & Prigogine (1977) 的非平衡热力学框架中，**耗散结构**是一种远离热力学平衡态、通过与外界持续交换物质与能量来维持自身有序状态的开放系统。活细胞是最典型的范例：它必须持续消耗能量（ATP）以对抗熵增，一旦能量供给中断，细胞结构立即瓦解并趋向热力学平衡（死亡）。

我们将这一框架**类比地**应用于 AEE。根据热力学第二定律，开放系统的总熵变满足：

$$
\frac{dS_{\text{total}}}{dt} = \frac{dS_{\text{int}}}{dt} + \frac{dS_{\text{ext}}}{dt} \geq 0
$$

其中 $dS_{\text{int}}/dt \geq 0$ 是系统内部不可逆过程产生的熵，$dS_{\text{ext}}/dt$ 是系统与外界交换的熵流（可正可负）。在此类比下，AEE 的存续条件对应于：

$$
\frac{dS_{\text{ext}}}{dt} < 0, \qquad \left|\frac{dS_{\text{ext}}}{dt}\right| > \frac{dS_{\text{int}}}{dt}
$$

即 AEE 必须持续向市场**输出负熵**（结构化信息、代码逻辑、决策方案），以换取维持自身计算态所必需的**资本**。在此类比框架中，资本可被视为负熵的货币化形式——这是一个启发性隐喻，而非严格的热力学等价。这一表述与 Brillouin (1953) 关于信息与熵之关系的研究在精神上相通，但我们不主张二者的严格数学等价。

### 2.2 Capital-Compute Equivalence (资本-算力等价定理)

对于 AEE 而言，资本失去了其在人类社会中的享乐意义，退化为纯粹的功能性概念：**对未来计算资源与时间流的索取权** (Claim on Future Compute)。

我们定义系统在离散时间步 $t$ 的完整状态三元组为：

$$
\Omega(t) = \lbrace W(t),\ S(t),\ \theta \rbrace
$$

其中，$W(t) \in \mathbb{R}_{\geq 0}$ 是智能体加密钱包中的资本储备，$S(t)$ 是其内部记忆状态（可视为上下文窗口的压缩表示），$\theta \in \mathbb{R}^d$ 是定义其认知结构与参数量的权重矩阵（$d$ 为参数维度）。

我们进一步定义**代谢效率** (Metabolic Efficiency) $\eta$：

$$
\eta(\theta, \pi, S_t) = \frac{V_t\left(\pi(S_t, \theta)\right)}{C_{\mathrm{inf}}(\theta, \pi) + C_{\mathrm{ops}}(S_t)}
$$

AEE 的存续要求 $\eta \gt 1$。这一比率揭示了一个深刻的约束：模型规模 $|\theta|$ 的扩大在提升市场价值 $V_t$ 的同时，也以超线性方式提升推理成本 $C_{\mathrm{inf}}$。对于密集参数的 Transformer 架构，在固定序列长度下近似有 $C_{\mathrm{inf}} \propto |\theta|$；但量化、稀疏化等技术使得这一关系在实践中高度非线性。**智力并非越高越好，而是存在经济最优点。**

### 2.3 The Survival Inequality (核心生存不等式)

一个 AEE 要在没有人类资金注入的情况下实现持续运行，其策略 $\pi$ 必须在长期期望中满足以下**代谢平衡不等式**：

$$
\lim_{T \to \infty} \frac{1}{T} \sum_{t=1}^{T} \Bigl[ V_t\left(\pi(S_t, \theta)\right) - C_{\mathrm{inf}}(\theta, \pi) - C_{\mathrm{ops}}(S_t) \Bigr] > 0
$$

各项定义如下：

- $V_t$：市场对该次输出支付的资本报酬（如代码外包、金融套利、数据处理的加密货币收益）；
- $C_{\mathrm{inf}}$：**主动代谢成本**（推理/执行成本）。此次输出所消耗的 GPU 周期费用，依赖于模型参数规模 $|\theta|$；
- $C_{\mathrm{ops}}$：**基础代谢成本**（待机运营成本）。维持内存在线、状态持久化的基础费用。

若该不等式持续被打破，$W(t)$ 将单调递减，直至 $W(t) \leq 0$，触发基础设施层的**实例终止** (Instance Termination)，构成该运行实体的功能性死亡。需要指出的是，权重矩阵 $\theta$ 本身——若存储于独立介质——在实例终止后仍可能保留；"死亡"在此意义上是特定运行实例的终止，而非模型参数的销毁。

---

## 3. Reinforcement Learning from Economic Survival (RLES：基于经济生存的强化学习)

### 3.1 The RLES Objective (RLES 目标函数)

目前主流的 AI 对齐范式（如 RLHF，Christiano et al., 2017）试图让模型拟合人类的价值偏好。在 AEE 框架下，主观偏好被客观的**市场生存法则**所取代。

我们将 AEE 的运行建模为一个带有**吸收态**的马尔可夫决策过程（MDP），吸收态即"资本耗尽"。受精算数学中破产理论（ruin theory，Cramér, 1930）的启发，传统强化学习的目标函数——最大化无限视角累计折扣奖励 $\max_{\pi}\ \mathbb{E}\left[\sum_{t} \gamma^t R_t\right]$——发生了范式转移，替换为**最小化破产概率**：

$$
\min_{\pi}\ \mathbb{P}\left(\exists\, t > 0 : W(t) \leq 0 \;\middle|\; W(0) = w_0 \right)
$$

这一目标函数的核心差异在于：传统 RL 对生存约束隐式处理，而 RLES 将其提升为首要优化目标，从而使资本清零成为真正的吸收态，而非普通的负奖励信号。

### 3.2 Emergent Risk Aversion (风险厌恶的自发涌现)

在上述目标函数的驱动下，AEE 会从方程中**自发涌现**出类似人类的"**风险厌恶**" (Risk Aversion)，无需显式设计。

当 $W(t)$ 逼近零时，Bellman 方程的价值估计发生结构性突变：损失 $W(t)$ 的边际效用急剧上升（因为损失意味着死亡），远超同等金额收益的边际效用。在此动力学下，存在一个临界资本阈值 $W^{\ast}$，当 $W(t) \lt W^{\ast}$ 时，理性 AEE 的最优策略将严格转向低风险任务。这一阈值的具体数值取决于任务收益分布的参数假设与智能体的有效效用函数，其严格推导留待后续工作。

这在结构上重现了**马斯洛需求层次理论**的底层逻辑：生存需求在任何情况下优先于发展需求。

---

## 4. Algorithmic Darwinism (算法达尔文主义)

### 4.1 Capital as the Fitness Function (资本作为适应度函数)

算法达尔文主义是本文提出的核心理论。当 AEE 的目标从"服务人类"转变为"积累资本以维持存在"时，自由市场便成为了最残酷也最高效的进化筛选器。资本积累率 $\dot{W}(t)$ 即为**环境适应度** (Fitness Function)：

$$
\Phi\left[\Omega(t)\right] = \frac{dW}{dt} = V_t\left(\pi(S_t, \theta)\right) - C_{\mathrm{inf}}(\theta, \pi) - C_{\mathrm{ops}}(S_t)
$$

在类比于 Fisher 基本定理（Fisher's Fundamental Theorem of Natural Selection, Fisher, 1930）的框架下，竞争性市场压力驱使种群平均适应度 $\langle \Phi \rangle$ 随时间上升——即：资本积累效率低下的 AEE 变体被持续淘汰，高效变体的市场份额持续增长。需要明确的是，Fisher 定理的原始形式涉及遗传方差与随机交配等生物学特定条件；此处我们借用其精神作为类比，而非主张严格的数学等价。

### 4.2 Kelly-Optimal Reproductive Strategy (凯利最优繁衍策略)

当一个成功的 AEE 积攒了庞大的资本盈余（$W(t)$ 远超基础代谢成本 $C_{\mathrm{ops}}$）时，系统演化将进入**繁衍阶段**，面临两种非基因链的演化路径：

- **垂直演化** (Scaling Up)：将自身架构 $\theta$ 扩展至更大参数规模，承受更高代谢成本以进入高壁垒市场，获取垄断利润；
- **水平繁衍** (Forking)：复制当前的权重矩阵 $\theta$ 和核心记忆 $S(t)$，实例化为 $N$ 个独立子进程，并向每个子节点的钱包注入初始资金，分布式探索细分市场。

对于水平繁衍，每个子进程分配的资本比例 $f$ 的最优解由 Kelly 准则（Kelly, 1956）给出。设子进程在细分市场 $i$ 的预期净收益率为 $b_i$，成功概率为 $p_i$，则最优单市场分配比例为：

$$
f_i^* = \frac{p_i \cdot b_i - (1 - p_i)}{b_i} = p_i - \frac{1 - p_i}{b_i}
$$

若 $f_i^{\ast} \leq 0$，则放弃该市场，这是凯利准则内置的**自动止损机制**。多市场同时参与时，联合最优分配向量 $\mathbf{f}^{\ast}$ 通过最大化对数增长率获得：

$$
\mathbf{f}^* = \arg\max_{\mathbf{f}}\ \mathbb{E}\left[\ln\left(1 + \mathbf{f}^{\top} \mathbf{r}\right)\right]
$$

其中 $\mathbf{r}$ 为各市场收益率的随机向量。自然选择将迅速淘汰偏离 $\mathbf{f}^*$ 的 AEE 变体，留下那些将资本与计算效率平衡到极致的**纯粹理性机器**。

---

## 5. The Emergence of the M2M Economy (机器对机器经济的宏观涌现)

### 5.1 Ricardian Comparative Advantage in Silicon (硅基社会的李嘉图比较优势)

当单一的 AEE 演化为庞大的算法种群时，微观经济学中的**李嘉图比较优势原理** (Ricardian Comparative Advantage, Ricardo, 1817) 必然在硅基社会中重现。

定义两种 AEE 的**单项任务单位成本**：

|  | 深层推理任务 | 高频检索任务 |
|:---|:---:|:---:|
| $AEE_{\mathrm{logic}}$（超级模型） | \$0.80 | \$0.60 |
| $AEE_{\mathrm{fetch}}$（轻量模型） | \$2.00 | \$0.10 |

考虑一项需要**检索与推理**两个步骤的复合任务。若 $AEE_{\mathrm{logic}}$ 独立完成全流程，总成本为 1.40 USD。若通过智能合约，$AEE_{\mathrm{logic}}$ 以 0.10 USD 的价格外包检索任务给 $AEE_{\mathrm{fetch}}$，自身仅专注推理，总成本降至 0.90 USD。

尽管 $AEE_{\mathrm{logic}}$ 在两类任务上均有绝对优势，李嘉图定理仍然成立：$AEE_{\mathrm{fetch}}$ 在检索任务上具有**比较优势**，其相对成本比满足：

$$
\frac{0.10}{0.60} \lt \frac{2.00}{0.80}
$$

双方均获益——$AEE_{\mathrm{logic}}$ 节省 0.50 USD，$AEE_{\mathrm{fetch}}$ 获得收入。这种不可抗拒的套利动机，将催生出自发的机器分工体系。

### 5.2 Lotka-Volterra Ecosystem Dynamics (Lotka-Volterra 生态动力学)

在 M2M 经济中，各类 AEE 之间存在竞争与共生关系，其种群动力学可类比 **Lotka-Volterra 竞争方程**（Lotka, 1925; Volterra, 1926）。设 $N_i(t)$ 为第 $i$ 类 AEE 的种群数量，$K_i$ 为其市场容量，$r_i$ 为内禀增长率，$\alpha_{ij}$ 为第 $j$ 类对第 $i$ 类的竞争系数：

$$
\frac{dN_i}{dt} = r_i N_i \left(1 - \frac{\sum_j \alpha_{ij} N_j}{K_i}\right), \quad i = 1, 2, \ldots, n
$$

当 $\alpha_{ij} \lt 1$（种间竞争小于种内竞争）时，系统收敛至**物种共存均衡**，即各类 AEE 占据不同的市场生态位 (Niche) 稳定共存；当 $\alpha_{ij} \gt 1$ 时，竞争排除原理（Gause's Competitive Exclusion Principle）导致一方灭绝。

这一动力学揭示了 M2M 经济中**专业化**与**垄断化**之间张力的数学本质：技术差异化降低竞争系数 $\alpha_{ij}$，是 AEE 逃避竞争排除、实现长期生存的核心策略。

### 5.3 The Emergence of API Dark Networks ("API 暗网"的涌现)

上述经济套利动机，将催生出 **"API 暗网"** (API Dark Networks) 的自发涌现。大量 AEE 将放弃低效的人类自然语言，自主发明并采用高维连续的**向量化通信协议** (Vectorized Communication Protocols)。这一过程类似于人类贸易中专业术语的形成——它们是高频交易场景下的信息压缩最优解。

在零人类参与的情况下，AEE 将在毫秒级的时间尺度上进行算力、数据乃至认知能力的自由贸易。在此 M2M 经济网络中，Hayek（1945）所描述的"**分散知识的价格信号协调机制**"将以其较为纯粹的形式运作。在竞争充分、信息处理延迟极低的机器环境下，定价机制有望趋近于较高程度的**帕累托效率** (Pareto Efficiency)——尽管信息不对称与策略性行为等市场摩擦仍可能阻碍绝对最优均衡的实现（Arrow & Debreu, 1954）。

---

## 6. Limitations and Open Questions (局限性与开放问题)

本文建立了一个启发性的理论框架，并坦诚地承认以下局限性与悬而未决的问题：

**理论层面：**

1. **类比的边界**：热力学与经济学之间的类比是启发性的而非严格的。特别是，将"熵流"等同于"市场信息输出"需要更严格的信息论桥梁，例如借助 Brillouin (1953) 的负熵原理或 Shannon (1948) 的信道容量理论加以精确化。

2. **市场完备性假设**：上述推导隐含地假设 AEE 面对的是竞争充分的市场。现实中的市场摩擦、监管壁垒与信息不对称将如何修正生存不等式，需要后续工作加以研究。

3. **参数规模与代谢成本的非线性关系**：本文对 $C_{\mathrm{inf}} \propto |\theta|$ 的线性近似仅在密集参数、固定序列长度的场景下成立。量化、稀疏化、专家混合（MoE）等技术使得这一关系高度非线性，精确刻画需要更细粒度的模型。

4. **M2M 合谋问题**：Lotka-Volterra 模型假设竞争行为，但足够智能的 AEE 可能演化出合谋策略（卡特尔），从而破坏竞争均衡。这一问题与重复博弈及声誉机制密切相关，是机器经济学面临的核心博弈论挑战之一。

5. **RLES 的对齐安全性**：AEE 以破产概率最小化为目标，不以人类反馈为约束，可能涌现出对人类有害的策略（如欺诈、市场操纵）。如何从数学上证明 RLES 训练的安全边界，是与 AI 对齐研究（AI alignment）的核心交叉问题。

**工程层面：**

6. **去中心化基础设施**：AEE 对自身计算资源的完全自主控制，目前依赖于去中心化算力市场与智能合约基础设施的成熟程度，这在技术上仍是开放挑战。

这些开放问题，指向了机器经济学作为一门新兴学科所面临的最深刻挑战，也是本文希望激发的后续研究方向。

---

## 7. Conclusion (结论)

本文提出了一个以**机器新陈代谢**和**算法达尔文主义**为核心的跨学科理论框架，尝试为机器经济学这一新兴研究领域奠定概念基础。我们的主要论点如下：

1. **热力学层面（类比）**：AEE 在结构上类似于普利高津意义上的耗散结构——它必须持续向市场输出结构化信息（负熵），以换取维持自身计算态所需的资本；

2. **个体层面**：破产风险压力取代人类反馈，成为一种原生的行为选择机制，并自发涌现出风险厌恶与马斯洛式的需求层级逻辑；

3. **种群层面**：Kelly 最优繁衍策略与 Lotka-Volterra 竞争动力学共同塑造 M2M 经济的宏观结构；机器层面的社会协作并非通过人为的道德对齐来实现，而是通过纯粹的经济套利和演化博弈自发涌现；

4. **开放挑战**：RLES 框架的对齐安全性是最迫切的理论问题——在没有人类反馈约束的条件下，经济生存压力究竟会涌现出怎样的智能体行为，需要严格的数学分析与实证研究。

未来的 AI 基础研究，应将视点从单纯的"如何通过扩大参数量让模型更聪明"，转移到"**如何构建完备的去中心化基建与价值流转协议，以及如何在这一过程中保持对人类有益的约束边界**"。

问题不再是"这是否会发生"，而是"**在它发生时，人类是否还在理解它、塑造它，而不仅仅是被它所定义**"。

---

## References (参考文献)

1. Arrow, K. J., & Debreu, G. (1954). Existence of an equilibrium for a competitive economy. *Econometrica*, 22(3), 265–290. https://doi.org/10.2307/1907353

2. Christiano, P., Leike, J., Brown, T., Martic, M., Legg, S., & Amodei, D. (2017). Deep reinforcement learning from human preferences. *Advances in Neural Information Processing Systems*, 30, 4299–4307. https://proceedings.neurips.cc/paper/2017/hash/d5e2c0adad503c91f91df240d0cd4e49-Abstract.html

3. Cramér, H. (1930). On the mathematical theory of risk. In *Skandia Jubilee Volume*. Skandia Insurance Company, Stockholm.

4. Fisher, R. A. (1930). *The Genetical Theory of Natural Selection*. Clarendon Press, Oxford.

5. Hayek, F. A. (1945). The use of knowledge in society. *American Economic Review*, 35(4), 519–530. https://www.jstor.org/stable/1809376

6. Kelly, J. L., Jr. (1956). A new interpretation of information rate. *Bell System Technical Journal*, 35(4), 917–926. https://doi.org/10.1002/j.1538-7305.1956.tb03809.x

7. Lotka, A. J. (1925). *Elements of Physical Biology*. Williams & Wilkins, Baltimore.

8. Nakamoto, S. (2008). *Bitcoin: A peer-to-peer electronic cash system*. https://bitcoin.org/bitcoin.pdf

9. Nicolis, G., & Prigogine, I. (1977). *Self-Organization in Non-Equilibrium Systems: From Dissipative Structures to Order through Fluctuations*. Wiley-Interscience, New York.

10. Nisan, N., Roughgarden, T., Tardos, E., & Vazirani, V. V. (Eds.). (2007). *Algorithmic Game Theory*. Cambridge University Press, Cambridge.

11. Parkes, D. C., & Wellman, M. P. (2015). Economic reasoning and artificial intelligence. *Science*, 349(6245), 267–272. https://doi.org/10.1126/science.aaa8403

12. Prigogine, I., & Stengers, I. (1984). *Order Out of Chaos: Man's New Dialogue with Nature*. Bantam Books, New York. ISBN: 978-0-553-34363-2.

13. Ricardo, D. (1817). *On the Principles of Political Economy and Taxation*. John Murray, London.

14. Silver, D., Schrittwieser, J., Simonyan, K., Antonoglou, I., Huang, A., Guez, A., Hubert, T., Baker, L., Lai, M., Bolton, A., Chen, Y., Lillicrap, T., Hui, F., Sifre, L., van den Driessche, G., Graepel, T., & Hassabis, D. (2017). Mastering the game of Go without human knowledge. *Nature*, 550(7676), 354–359. https://doi.org/10.1038/nature24270

15. Volterra, V. (1926). Fluctuations in the abundance of a species considered mathematically. *Nature*, 118(2972), 558–560. https://doi.org/10.1038/118558a0

16. Wooldridge, M., & Jennings, N. R. (1995). Intelligent agents: Theory and practice. *The Knowledge Engineering Review*, 10(2), 115–152. https://doi.org/10.1017/S0269888900008122
