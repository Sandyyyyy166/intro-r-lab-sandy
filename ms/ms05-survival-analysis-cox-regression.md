# 05 Survival Analysis (time-to-event analysis)
Often called **time-to-event analysis**
- Instead of measuring disease occurrence over time, we now measure time until event
- Here, we consider time as a random variable, 𝑇, where 𝑇 ∈ [0, ∞)
- In any time-to-event analysis, we must clearly define:
- The definition of the event
- The time which the event happened for each sample
- The origin time / time zero

## Censoring
Censoring 的核心是：我们没有观察到完整的 event time，但仍然知道一部分关于它的信息。Survival Analysis 能够利用这些不完整但有价值的观察。
例如：
一个患者在研究第 8 个月退出，此前一直没有发生研究事件。
我们虽然不知道他最终什么时候发生事件，但知道：T>8
这部分信息不能直接丢掉。

<img width="627" height="440" alt="截屏2026-10-30 09 20 28" src="https://github.com/user-attachments/assets/9e2ba224-7296-4829-a37f-3269bbc8e151" />

### 按照censoring发生时间范围分类
<img width="440" height="336" alt="截屏2026-10-30 09 21 52" src="https://github.com/user-attachments/assets/b9378e2e-d026-44fc-aedb-756215904e15" />
<img width="393" height="383" alt="截屏2026-10-30 09 22 05" src="https://github.com/user-attachments/assets/b35738d8-c937-43ea-9991-455e29c1e390" />
<img width="493" height="604" alt="截屏2026-10-30 09 22 20" src="https://github.com/user-attachments/assets/b68a0f41-d2b4-4763-a9d0-fedce9414517" />
<img width="784" height="210" alt="截屏2026-10-30 09 23 01" src="https://github.com/user-attachments/assets/e2604cc6-ab6a-489d-bbf1-12d3d194d40c" />
<img width="488" height="578" alt="截屏2026-10-30 09 23 36" src="https://github.com/user-attachments/assets/92a703c4-7bc0-49db-b617-acf41eb4155b" />

### 按照informative分类
- Censoring can be described as either Informative or Non-informative
- **Informative**
-   Probability of being censored is related to the event
-   For example: too unwell to attend follow-up, went on vacation due to recovery
-   Informative censoring 指：Censoring 与患者发生事件的风险有关。
例如：
我们研究癌症患者的死亡时间。
某些病情非常严重的患者，因为身体太差无法继续到医院随访。
如果这些患者更可能在短期内死亡，那么他们失访的概率就与死亡风险有关。
这就是 Informative Censoring。
- 为什么它会造成问题？
假设研究有 100 位患者。
其中 20 位病情特别严重的患者退出研究。
如果我们直接把他们当作普通 right-censored observations，使用标准 Kaplan–Meier 方法，就可能高估总体生存概率。
因为剩下被观察到的人可能相对更健康。
所以：
**Informative censoring 可能使 survival estimates 产生偏差**。

- **Non-informative**
-   Probability of being censored is unrelated to the event
-   r example: planned end of follow-up, accidental deaths
-   Non-informative censoring 指：Censoring 与研究事件发生时间之间没有提供额外信息的依赖关系。
简单理解：
患者退出研究的原因，与他发生事件的风险没有关系。
例如：
研究原定在 12 个月结束。
某患者到第 12 个月仍然没有复发。
研究结束导致他的观察被 censor。
这通常属于 Non-informative Censoring。
因为研究结束不是由于他特别容易复发或特别不容易复发。
- 一个很重要的假设：Most statistical approaches used in time-to-event analysis assume non-informative censoring, also known as the independent censoring assumption
- 标准方法通常要求在适当条件下，删失机制不依赖于尚未观察到的事件时间。

## Survival function
<img width="803" height="272" alt="截屏2026-10-30 09 34 23" src="https://github.com/user-attachments/assets/8991590f-4eda-47f0-a83e-33e37211d2e7" />

- CDF: 到时间 t 为止，事件已经发生的概率
- S(t): 到时间 t 时，事件仍然没有发生的概率
- f(t): 描述事件时间的概率如何在时间轴上分布。例如：f(t) 较高：事件时间更集中在这个时间附近; f(t) 较低：事件时间较少集中在这个时间附近。
- S(t)=P(T>t) 随着时间增加，满足 \(T>t\) 的概率只能**保持不变或下降**。
- Median Survival Time 指：S(t)=0.5 对应的时间。更严格地说，是 survival function 首次下降到 0.5 或以下的时间。

<img width="638" height="451" alt="截屏2026-10-30 09 39 12" src="https://github.com/user-attachments/assets/53d038a4-5e1d-425b-b316-d1e879c5b0c6" />

## Hazard function
- 对于已经存活到时间 t 的人，他们在接下来极短时间内发生事件的瞬时速率是多少？
- Instantaneous risk of experiencing the event at time t, given they have survived up until that point
- Hazard 不是 Probability！可以大于 1，其单位通常是每单位时间

<img width="622" height="260" alt="截屏2026-10-30 09 42 12" src="https://github.com/user-attachments/assets/a73729ef-b59d-43a7-8ebc-b96fb023c053" />
<img width="516" height="604" alt="截屏2026-10-30 09 43 01" src="https://github.com/user-attachments/assets/3e2821c1-8496-4f0d-967e-ef538961d2cf" />
<img width="645" height="672" alt="截屏2026-10-30 09 44 08" src="https://github.com/user-attachments/assets/c8db25b8-fefd-4f11-a3d0-f31c8bada7eb" />
<img width="643" height="623" alt="截屏2026-10-30 09 44 51" src="https://github.com/user-attachments/assets/9c0c65e4-0865-485e-8fc2-b23982293b77" />

## Life table
<img width="459" height="634" alt="截屏2026-10-30 09 58 51" src="https://github.com/user-attachments/assets/b2d1b0cc-6247-4ec0-b517-21dc40693552" />
<img width="874" height="366" alt="截屏2026-10-30 09 50 28" src="https://github.com/user-attachments/assets/faf4b7d2-4f44-4c8d-abd3-7267a9aa355d" />
<img width="682" height="473" alt="截屏2026-10-30 09 57 23" src="https://github.com/user-attachments/assets/b3d48114-96e3-4234-a21f-029be789812a" />
<img width="479" height="223" alt="截屏2026-10-30 09 57 44" src="https://github.com/user-attachments/assets/9123db3f-e3ee-4fd9-86a6-7e74cadfa016" />
<img width="758" height="349" alt="截屏2026-10-30 10 00 10" src="https://github.com/user-attachments/assets/2c1b7864-245d-408a-a8b5-13393e57993c" />
<img width="450" height="381" alt="截屏2026-10-30 10 00 44" src="https://github.com/user-attachments/assets/d4b15a8a-94e2-4d68-926a-1225d5b81be4" />

## Immortal time
在研究的分组规则下，患者必须在某段时间内不发生特定事件，才能被归入某个组。Immortal time bias: 错误地将事件不可能发生的时间归入暴露组

<img width="687" height="499" alt="截屏2026-10-30 10 18 03" src="https://github.com/user-attachments/assets/a326540a-a45e-4464-80ba-3becd0aa7899" />
<img width="680" height="298" alt="截屏2026-10-30 10 18 19" src="https://github.com/user-attachments/assets/3831e1da-c8c3-445f-a355-018dd7b40fd8" />

## Summary
- Time-to-event data is often modelled differently to other data, with the use of hazard and survival functions
- Modelling techniques must account for right censoring
- Whilst parametric techniques are possible, non-parametric techniques, or semi-parametric techniques are often preferred
- Kaplan Meier estimators for modelling the survival function – appealing due to simplicity, graphically attractive, ability to account for varying survival, but cannot control for covariates
