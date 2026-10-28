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
Directed：箭头有方向，表示假设的因果方向。
Acyclic：不能沿着箭头绕一圈回到原来的变量。
Graph：由节点（nodes）和箭头（edges）组成。





