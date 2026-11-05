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

### Step 7B: equity-weighted objective 权重改变的是政策评价标准，不是实际服务人数
<img width="778" height="271" alt="截屏2026-11-05 10 29 01" src="https://github.com/user-attachments/assets/333333e5-1f85-4e12-b0be-2441bae838b5" />
<img width="430" height="264" alt="截屏2026-11-05 10 28 47" src="https://github.com/user-attachments/assets/8bf84bc5-55cb-4fd5-8834-2c66117e2ae6" />

### MILP = Mixed Integer Linear Programming（混合整数线性规划）
- Mixed（混合）：模型同时有整数变量 \(x_i\) 和连续变量 \(y_i\)。
- Integer（整数）：团队数量必须是整数。
- Linear（线性）：公式中没有决策变量之间相乘、变量平方等非线性关系。
- Programming（规划）：这里指数学优化，不是写程序代码。
- 所以 MILP 本质上就是：在满足一系列线性约束的情况下，寻找最优的变量组合，其中部分变量必须是整数。

<img width="630" height="387" alt="截屏2026-11-05 10 29 37" src="https://github.com/user-attachments/assets/d96dcb31-d8c7-4827-9cbb-79b6ba56ade2" />
<img width="766" height="286" alt="截屏2026-11-05 10 32 10" src="https://github.com/user-attachments/assets/6dc05555-2ca5-4976-8f8e-c736bbd095ac" />

### Coverage：Higher service volume does not necessarily mean higher coverage
<img width="672" height="357" alt="截屏2026-11-05 10 33 21" src="https://github.com/user-attachments/assets/01eb6a14-1d4c-4829-9976-e6e29fa7dc5d" />
<img width="393" height="652" alt="截屏2026-11-05 10 34 05" src="https://github.com/user-attachments/assets/7e0af5d1-5496-46e0-82aa-120dacdbb6a8" />
<img width="458" height="650" alt="截屏2026-11-05 10 36 30" src="https://github.com/user-attachments/assets/92cc3628-f672-4b4f-af7f-44440d57b9e1" />

## What the solver is doing
### feasible
<img width="739" height="413" alt="截屏2026-11-05 10 38 36" src="https://github.com/user-attachments/assets/7034556f-7ecf-4644-b3d6-8a68d5e91d59" />
<img width="611" height="610" alt="截屏2026-11-05 10 39 15" src="https://github.com/user-attachments/assets/136df307-b688-4645-8d0b-6c85cc6ebd06" />

### infeasible
<img width="484" height="656" alt="截屏2026-11-05 10 41 50" src="https://github.com/user-attachments/assets/f0a7ad55-f3b2-422e-bb8f-25b1923696b6" />
<img width="614" height="672" alt="截屏2026-11-05 10 43 35" src="https://github.com/user-attachments/assets/d138b82c-65e5-44aa-8800-2b8413e4cfec" />
<img width="458" height="432" alt="截屏2026-11-05 10 43 59" src="https://github.com/user-attachments/assets/953b3acc-2f40-47d2-b278-44a0beca6d0b" />

### Feasible region
<img width="713" height="355" alt="截屏2026-11-05 10 44 55" src="https://github.com/user-attachments/assets/474738da-6711-4713-9011-ba678c5a701d" />

- LP（Linear Programming）：允许连续变量，因此三角形中的所有点(infinite)都可以是可行解。
- MILP（Mixed Integer Linear Programming）：要求部分变量为整数，因此只能选择满足整数限制的点。

<img width="710" height="428" alt="截屏2026-11-05 10 45 21" src="https://github.com/user-attachments/assets/142d963c-6365-4f9e-a081-1adaa488d44c" />
<img width="628" height="565" alt="截屏2026-11-05 10 46 55" src="https://github.com/user-attachments/assets/4e1cb761-9089-4308-9ea2-8d328fc35932" />
<img width="610" height="378" alt="截屏2026-11-05 10 47 28" src="https://github.com/user-attachments/assets/d882bdfe-dc0a-4f88-b365-ccca1d19d9a6" />
<img width="583" height="223" alt="截屏2026-11-05 10 58 29" src="https://github.com/user-attachments/assets/77b5f757-f42b-4ae2-9221-1a57ce4f7808" />
<img width="384" height="670" alt="截屏2026-11-05 10 58 51" src="https://github.com/user-attachments/assets/1f88d741-27f8-46cd-90a5-deb446de57ee" />
<img width="386" height="622" alt="截屏2026-11-05 10 59 10" src="https://github.com/user-attachments/assets/6a239943-7a2c-4429-9c52-615e9fb5d5df" />
<img width="444" height="460" alt="截屏2026-11-05 10 59 36" src="https://github.com/user-attachments/assets/3e18a46e-679a-4086-88b8-9c92e72bce27" />

### LP relaxation
<img width="387" height="649" alt="截屏2026-11-05 10 48 09" src="https://github.com/user-attachments/assets/bd84ac59-b5d2-41b0-815d-fbb56e52d05d" />
<img width="420" height="456" alt="截屏2026-11-05 10 48 24" src="https://github.com/user-attachments/assets/e607fc54-0587-4935-9195-eb0a96f828a2" />
<img width="407" height="612" alt="截屏2026-11-05 10 48 56" src="https://github.com/user-attachments/assets/e09b117c-3ded-4343-b7f4-7619fa31de0b" />
<img width="619" height="640" alt="截屏2026-11-05 10 49 35" src="https://github.com/user-attachments/assets/11032bd1-8c12-46ce-8a40-1456e9244da8" />

### Branch-and-Bound 分支定界法
<img width="613" height="668" alt="截屏2026-11-05 10 51 01" src="https://github.com/user-attachments/assets/4430d9d6-31af-4e03-95d7-19342d472127" />
<img width="509" height="664" alt="截屏2026-11-05 10 52 02" src="https://github.com/user-attachments/assets/72895bea-a267-4c60-a150-e67e7b4f3b84" />
<img width="595" height="319" alt="截屏2026-11-05 10 52 53" src="https://github.com/user-attachments/assets/f3c46985-20c0-4a6b-8f73-295c2c1fa8d5" />

### Solver gap and optimality gap 最优性差距
<img width="492" height="489" alt="截屏2026-11-05 10 53 14" src="https://github.com/user-attachments/assets/dd5bca90-3e23-4cab-9981-8525c811efb8" />
<img width="406" height="598" alt="截屏2026-11-05 10 54 52" src="https://github.com/user-attachments/assets/65b70500-6933-4915-9c37-561f9eab8dce" />
<img width="426" height="279" alt="截屏2026-11-05 10 55 06" src="https://github.com/user-attachments/assets/04340683-1f76-48df-9221-60aefc31688f" />

### Matrix form 就是把很多条数学公式压缩成两个矩阵表达式
<img width="511" height="478" alt="截屏2026-11-05 11 15 57" src="https://github.com/user-attachments/assets/926b41b3-b145-4b9d-a810-c4de8fb50720" />
<img width="342" height="231" alt="截屏2026-11-05 11 17 14" src="https://github.com/user-attachments/assets/afeec391-f452-427d-ac80-f1e3fb28825d" />

