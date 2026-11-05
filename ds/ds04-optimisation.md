# 04 Mathematical Optimisation and Data-Informed Health Policy
<img width="620" height="653" alt="截屏2026-11-05 09 19 05" src="https://github.com/user-attachments/assets/e648c732-683e-4607-b6c7-6ba6ac5ab326" />

## Mathematical Optimisation Intro
<img width="770" height="387" alt="截屏2026-11-05 09 21 41" src="https://github.com/user-attachments/assets/6de1f23a-2bd5-4c19-ab98-2335d9c6277d" />
<img width="620" height="654" alt="截屏2026-11-05 09 26 02" src="https://github.com/user-attachments/assets/a0d6d1c9-ff5f-4941-8a3b-addbe82353b0" />
<img width="461" height="661" alt="截屏2026-11-05 09 26 41" src="https://github.com/user-attachments/assets/5906d050-6e53-4b63-a5c6-21c4e11ff53a" />
<img width="611" height="496" alt="截屏2026-11-05 09 27 26" src="https://github.com/user-attachments/assets/abdde456-a185-4edf-bf95-80abadeda1e5" />

Calculation 是计算一个结果；Optimisation 是在多个可行选择之间寻找最好的方案。
When does a decision become an optimisation problem?
-> Scarcity creates trade-offs.
**优化结果取决于我们设定的目标、约束条件和输入数据。**

<img width="718" height="293" alt="截屏2026-11-05 09 33 13" src="https://github.com/user-attachments/assets/bdcc7ba3-b438-4e24-a23d-6c91454baf2a" />

### 情景
<img width="561" height="495" alt="截屏2026-11-05 09 30 54" src="https://github.com/user-attachments/assets/5c8ec72c-e80e-4003-a59d-8364496417c5" />
<img width="616" height="663" alt="截屏2026-11-05 09 31 13" src="https://github.com/user-attachments/assets/5ff39fbf-eb28-42fb-aab7-b6da1bdf1d5a" />
<img width="515" height="306" alt="截屏2026-11-05 09 31 31" src="https://github.com/user-attachments/assets/595614b2-e573-45d2-9e00-57e2190002f7" />
<img width="609" height="584" alt="截屏2026-11-05 09 32 05" src="https://github.com/user-attachments/assets/034c06f4-9ea7-465f-8695-2824c96e9e52" />

## From prediction to decisions: Prediction provides information, but Optimisation makes decisions under constraints.
<img width="750" height="391" alt="截屏2026-11-05 09 34 29" src="https://github.com/user-attachments/assets/9a73ffb9-8363-4903-b47e-5fc9bfc7407c" />
<img width="573" height="338" alt="截屏2026-11-05 09 35 29" src="https://github.com/user-attachments/assets/e41b5377-cd27-4212-9155-fbef5e765526" />
<img width="452" height="394" alt="截屏2026-11-05 09 48 23" src="https://github.com/user-attachments/assets/b324c0e1-98ca-4ec4-bcf5-aff30e644631" />

A Decision Model is Not a Causal Model.
Operational capacity ≠ Causal health benefit
服务能力增加，不等于已经证明健康结果改善。
如果我们的目标是最大化健康改善，而不是最大化服务量，就需要额外的因果证据。

## Formulating the Allocation Model 把一个现实中的资源分配问题，翻译成计算机能够求解的数学模型
### Step 1: Define the Index and Parameters 这些都是parameter
<img width="482" height="364" alt="截屏2026-11-05 09 51 44" src="https://github.com/user-attachments/assets/ff23e750-3f5f-440f-9059-f9a5c6bfb806" />

### Step 2: Define the Decision Variables
<img width="778" height="245" alt="截屏2026-11-05 09 53 15" src="https://github.com/user-attachments/assets/b54b9c21-cb1f-4e1e-a670-8d48206b9909" />

### Step 3: demand constraint 计入的服务量不能超过预计需求
<img width="776" height="166" alt="截屏2026-11-05 09 54 49" src="https://github.com/user-attachments/assets/7f9d6768-903c-43fd-ae8f-27d06ab37a4b" />

### Step 4: capacity constraint 计入的服务量不能超过团队能够提供的服务能力
<img width="776" height="160" alt="截屏2026-11-05 09 55 11" src="https://github.com/user-attachments/assets/d5e7e01d-1277-4772-b348-5e3f5e66b5cb" />

### Step 5: hosting constraint 分配的团队数量不能超过机构能够容纳的上限
<img width="770" height="157" alt="截屏2026-11-05 09 55 33" src="https://github.com/user-attachments/assets/8ea5f4ce-50f6-44a3-b2ba-7693613e47bc" />

### Step 6: budget constraint
<img width="770" height="231" alt="截屏2026-11-05 09 57 48" src="https://github.com/user-attachments/assets/add97b27-ff19-4a95-a1d4-d9e93d0eac25" />

### Step 7A efficiency objective 最大化所有医疗机构的总服务量
<img width="709" height="206" alt="截屏2026-11-05 09 59 02" src="https://github.com/user-attachments/assets/7f4d60fe-97ae-4d28-8b29-50e6b96ae978" />

