#05 Survival Analysis (time-to-event analysis)
Often called **time-to-event analysis**
 Instead of measuring disease occurrence over time, we now measure time until
event
 Here, we consider time as a random variable, 𝑇, where 𝑇 ∈ [0, ∞)
 In any time-to-event analysis, we must clearly define:
 The definition of the event
 The time which the event happened for each sample
 The origin time / time zero

## Censoring
Censoring 的核心是：我们没有观察到完整的 event time，但仍然知道一部分关于它的信息。Survival Analysis 能够利用这些不完整但有价值的观察。
例如：
一个患者在研究第 8 个月退出，此前一直没有发生研究事件。
我们虽然不知道他最终什么时候发生事件，但知道：T>8
这部分信息不能直接丢掉。

<img width="627" height="440" alt="截屏2026-10-30 09 20 28" src="https://github.com/user-attachments/assets/9e2ba224-7296-4829-a37f-3269bbc8e151" />

### 按照发生时间分类
<img width="440" height="336" alt="截屏2026-10-30 09 21 52" src="https://github.com/user-attachments/assets/b9378e2e-d026-44fc-aedb-756215904e15" />
<img width="393" height="383" alt="截屏2026-10-30 09 22 05" src="https://github.com/user-attachments/assets/b35738d8-c937-43ea-9991-455e29c1e390" />
<img width="493" height="604" alt="截屏2026-10-30 09 22 20" src="https://github.com/user-attachments/assets/b68a0f41-d2b4-4763-a9d0-fedce9414517" />
<img width="784" height="210" alt="截屏2026-10-30 09 23 01" src="https://github.com/user-attachments/assets/e2604cc6-ab6a-489d-bbf1-12d3d194d40c" />
<img width="488" height="578" alt="截屏2026-10-30 09 23 36" src="https://github.com/user-attachments/assets/92a703c4-7bc0-49db-b617-acf41eb4155b" />

### 按照informative分类
 Censoring can be described as either Informative or Non-informative
 Informative
o Probability of being censored is related to the event
o For example: too unwell to attend follow-up, went on vacation due to recovery
 Non-informative
o Probability of being censored is unrelated to the event
o For example: planned end of follow-up, accidental deaths
 Most statistical approaches used in time-to-event analysis assume non-informative censoring, also known as the independent censoring assumption

