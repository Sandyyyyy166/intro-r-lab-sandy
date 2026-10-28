# 03 Causal Inference and DAG
Correlation ≠ Causation
两个变量相关，不代表其中一个导致另一个。
比如课件展示了人造黄油消费量和离婚率的相关性，但这并不能证明吃人造黄油导致离婚。

三种 Research Questions
- Descriptive：发生了什么？
- Predictive：能不能预测什么会发生？
- Causal：如果我们改变 X，Y 会不会因此改变？

- Counterfactual（反事实）
对同一个患者，我们想知道：
- 如果接受 Treatment A，血压是多少？
- 如果接受 Treatment B，血压是多少？
但现实中，同一个人在同一条件下只能接受其中一种治疗，所以无法同时观察两个结果。
另一个没有实际发生、但我们希望知道的结果，就是 counterfactual outcome。
这就是 causal inference 的核心困难：我们无法同时观察同一个人的两个潜在结果。

## Confounding
Common cause of both the exposure and the outcome.
一个变量同时影响 Exposure（暴露因素）和 Outcome（结局），从而可能干扰我们对两者因果关系的判断。
confounding causes bias

## DAG
<img width="765" height="333" alt="截屏2026-10-28 09 45 11" src="https://github.com/user-attachments/assets/4b39a072-23a1-4799-955c-1cd909ac6743" />
<img width="707" height="357" alt="截屏2026-10-28 09 46 19" src="https://github.com/user-attachments/assets/4de426f2-1c96-4b52-a1f7-d44a17fc8a38" />

- Directed：箭头有方向，表示假设的因果方向。
- Acyclic：不能沿着箭头绕一圈回到原来的变量。
- Graph：由节点（nodes）和箭头（edges）组成。

### 概念合集
- Backdoor path：一条从 Exposure 到 Outcome 的非因果路径。
- Confounder：可能使 Exposure–Outcome 关系产生混杂的共同原因。
- Collider：路径上两个箭头同时指向的节点。
- Causal Path（因果路径）：箭头是不是一直从 A 指向 Y？可以是 A -> B -> C -> Y。但是A <- C <- Y就不是causal因为需要从A就是exposure出发。
- Open Path（开放路径）：这条路径有没有被 d-separation rules 阻断？这条路径可以传递统计关联association。它不代表因果关系，只代表这条路径没有被阻断。例如，在给定的 conditioning 条件下，C 同时影响 A 和 Y，DAG 允许 A 和 Y 可以通过 C 产生统计关联。
- Blocked path：这条路径在给定调整条件下被阻断，不会通过这条路径传递关联。
  
<img width="603" height="383" alt="截屏2026-10-28 09 50 23" src="https://github.com/user-attachments/assets/caafb580-9101-425e-8b59-9e601be23655" />
<img width="633" height="339" alt="截屏2026-10-28 09 50 45" src="https://github.com/user-attachments/assets/a5159017-b54f-49f6-b0e8-f7326056a9cd" />
<img width="566" height="369" alt="截屏2026-10-28 09 51 15" src="https://github.com/user-attachments/assets/d2216373-53bc-430b-aedc-a75e9fe85e45" />

### d-separation rules
<img width="801" height="352" alt="截屏2026-10-28 09 49 31" src="https://github.com/user-attachments/assets/79b8cc0b-4b3d-41e2-92c8-cec48d3b05e1" />
<img width="587" height="296" alt="截屏2026-10-28 10 16 13" src="https://github.com/user-attachments/assets/6d5797d4-854d-4a62-9559-549a35decb55" />


- **Open path**：这条路径可以传递统计关联。
- **Blocked path**：这条路径在给定调整条件下被阻断，不会通过这条路径传递关联。

- 我们的目标是block backdoor paths to eliminate bias。
- Conditioning on C = 在分析中控制 C，例如按 C 分层，或者在 regression 中调整 C。
- Conditioning 有时候会关闭 path，有时候反而会打开 path。所以要考虑四个 rules。

<img width="578" height="143" alt="截屏2026-10-28 09 58 12" src="https://github.com/user-attachments/assets/25890d5e-d98d-404f-9b6b-f6736b22546f" />

- **rule 1 没有控制任何变量时，路径上出现 Collider，就会阻断这条路径。**
- 在没有 conditioning 的情况下，A -> C <- Y 这条路径默认是 blocked。因为 A 和 Y 都影响 C，并不意味着 A 和 Y 本身就有关联。

<img width="663" height="298" alt="截屏2026-10-28 09 54 14" src="https://github.com/user-attachments/assets/70922432-e568-4e86-bfe6-77e7e1d58ae2" />

- **rule 2 控制路径上的 Non-collider，就会阻断这条路径。**
- 这里 Non-collider 指的是路径上没有两个箭头同时指向它的变量。
A <- L -> Y L同时影响 A 和 Y；
如果不控制 L，这条路径是 open 的，可能产生 confounding bias；
但如果我们控制 L 这条路径就会被 blocked。

<img width="637" height="246" alt="截屏2026-10-28 09 56 49" src="https://github.com/user-attachments/assets/e1016373-4273-458e-bcf1-75ac24ea0d95" />

- **rule 3 控制 Collider，会打开原本被阻断的路径。**
- A -> C <- Y 刚刚 Rule I 告诉我们，这条路径默认 blocked；
但如果我们控制 C 这条路径反而变成 Open：
举个例子：
假设 A 是学术能力，Y 是体育能力，而 C 是被某所大学录取。
学术能力强可以提高录取机会，体育能力强也可以提高录取机会。
在所有申请者中，学术能力和体育能力可能互不相关。
但如果我们只研究已经被录取的人：
- 学术能力较弱的录取者，可能更依赖体育能力。
- 体育能力较弱的录取者，可能更依赖学术能力。
于是我们可能观察到两者之间的负相关。
这个关联是由于**筛选已录取学生（conditioning on collider）**产生的。
它叫：
Collider Bias（碰撞偏倚）。
变成open就是A和Y产生关联了
<img width="632" height="265" alt="截屏2026-10-28 09 57 14" src="https://github.com/user-attachments/assets/71e7d584-3ec5-41f4-82c5-aaee603e6ea7" />
<img width="678" height="622" alt="截屏2026-10-28 10 31 07" src="https://github.com/user-attachments/assets/243f0489-a1b4-46b7-a178-076c41134cd5" />
<img width="683" height="517" alt="截屏2026-10-28 10 32 08" src="https://github.com/user-attachments/assets/51cfa0b4-5e4e-4b8f-9787-db0cc69bf7b5" />

- **rule 4 控制 Collider 的 Descendant，也会打开路径。**
- 控制 Collider 的后代也可能引入 collider bias。

<img width="602" height="316" alt="截屏2026-10-28 10 01 35" src="https://github.com/user-attachments/assets/0c6e6f22-1432-4690-9f3b-0c653f63ebd8" />









