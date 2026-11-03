# 02 Statistical and interpretable predictive modelling
什么是 Interpretable（可解释）？
假设两个模型都预测某病人有 80% 的患病概率。
模型 A 只告诉你：
患病概率 = 80%。
模型 B 除了给出概率，还能让你研究：
年龄、血压等变量如何影响模型的预测？
模型 B 就更容易进行解释。
在医疗领域，这一点尤其重要，因为医生不仅关心预测结果，还需要理解模型依据了什么信息。
不过，可解释不代表具有因果关系。模型发现年龄与疾病有关，不等于年龄是模型所观察到的全部关联的直接原因。
**Data Science 使用数据研究问题；Predictive Modelling 用数据预测结果；Interpretability 关注如何理解模型的预测依据。**
- Feature / Predictor（特征、预测变量）：模型用来预测的信息，给的条件，例如年龄、BMI。
- Target / Outcome / Label（目标、结果、标签）：模型想预测的答案，例如是否属于高风险组。

<img width="553" height="353" alt="截屏2026-11-03 09 20 43" src="https://github.com/user-attachments/assets/e1537784-9116-4309-9eda-3fd183808322" />
<img width="738" height="319" alt="截屏2026-11-03 09 25 56" src="https://github.com/user-attachments/assets/93c80263-8828-4949-9ed1-054221b4e6f3" />
- Longitudinal Data 是指对同一个对象，在不同时间点重复测量得到的数据。
- Analysis Window 就是决定：我们要使用哪些时间点的信息？
- Feature Engineering 就是把原始数据转换成更适合模型学习的特征。
- 为什么要 One Row per Liver？因为我们最终想预测的是每个肝脏的风险类别，而不是每一次测量的风险类别。
这也为后面理解 Data Leakage（数据泄漏） 打下基础：如果把同一个肝脏的不同时间点随机分配到训练集和测试集，就可能让模型在测试时遇到已经见过的肝脏，导致评估结果过于乐观。
- Fit（拟合、训练）：让模型根据已知数据学习规律。
- Evaluate（评估）：用没有参与训练的数据，检查模型能不能预测正确。
- 你可以把它理解成：
- Fit = 平时做练习题。
- Evaluate = 用新题目参加考试。

## 模块一：Formulating the Prediction Problem
<img width="594" height="660" alt="截屏2026-11-03 09 28 07" src="https://github.com/user-attachments/assets/a3c96a00-5c8a-4b29-9228-396d85ddbed2" />
