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
> [!TIP]
> 英文	中文	一句话记忆
> Feature	特征	模型的输入
> Target	目标变量	模型要预测的答案
> Classification	分类	预测属于哪个类别
> Regression	回归	预测连续数值
> Training / Development	训练 / 开发数据	用来学习规律、开发模型
> Validation	验证数据	用来比较模型、选择参数
> Test	测试数据	最后评估模型
> Data Leakage	数据泄漏	模型提前获得不应该知道的信息

<img width="594" height="660" alt="截屏2026-11-03 09 28 07" src="https://github.com/user-attachments/assets/a3c96a00-5c8a-4b29-9228-396d85ddbed2" />
<img width="616" height="661" alt="截屏2026-11-03 09 43 25" src="https://github.com/user-attachments/assets/2da1f4ef-65e6-4db0-a5ab-789264329cc5" />
<img width="442" height="471" alt="截屏2026-11-03 09 43 38" src="https://github.com/user-attachments/assets/727122fd-a017-4382-91e1-542c02c42394" />
<img width="615" height="649" alt="截屏2026-11-03 09 44 00" src="https://github.com/user-attachments/assets/72de75f3-1051-42eb-a87a-01139605eac6" />
<img width="619" height="468" alt="截屏2026-11-03 09 44 15" src="https://github.com/user-attachments/assets/4f1fd297-944b-42fe-90d1-e78b25363840" />
<img width="562" height="590" alt="截屏2026-11-03 09 44 41" src="https://github.com/user-attachments/assets/bb3cb7ff-df7e-48a2-b200-ba3530596960" />
<img width="582" height="676" alt="截屏2026-11-03 09 45 00" src="https://github.com/user-attachments/assets/d00b57d7-716a-499b-8ba5-f3e4798f7568" />
<img width="765" height="271" alt="截屏2026-11-03 09 47 53" src="https://github.com/user-attachments/assets/ee3cdc75-5eaa-40c2-a670-b38b9f089753" />
<img width="627" height="621" alt="截屏2026-11-03 09 45 12" src="https://github.com/user-attachments/assets/d7928b5c-cf68-44a4-abc0-53cfa734a9d2" />
<img width="485" height="646" alt="截屏2026-11-03 09 45 27" src="https://github.com/user-attachments/assets/e47d4561-8d5f-423f-80eb-75581d40a923" />
<img width="425" height="677" alt="截屏2026-11-03 09 45 42" src="https://github.com/user-attachments/assets/e38c22a4-c47b-4490-a795-d13ca61002b6" />
<img width="622" height="498" alt="截屏2026-11-03 09 45 57" src="https://github.com/user-attachments/assets/5e2b3ef4-8a3d-41dc-b667-c57dd6814f4a" />

> [!IMPORTANT]
> 模型开发不能偷看测试数据的答案，也不能通过预处理、重复对象或身份标识间接获得不应该知道的信息。

<img width="461" height="448" alt="截屏2026-11-03 09 49 29" src="https://github.com/user-attachments/assets/4b15ea6a-5242-4e6b-8f3f-241e79c31e1d" />
<img width="336" height="126" alt="截屏2026-11-03 09 49 15" src="https://github.com/user-attachments/assets/5c0ceecb-57e5-4172-a25f-4f4782c5f91f" />
<img width="379" height="578" alt="截屏2026-11-03 09 50 01" src="https://github.com/user-attachments/assets/866a6027-22e8-4f91-8af8-503c3f2b8c72" />
<img width="555" height="463" alt="截屏2026-11-03 09 50 27" src="https://github.com/user-attachments/assets/062d2842-4ac1-4159-8cf6-b5b077590fba" />

> [!IMPORTANT]
> Cross-validation 不只是重新训练模型，还需要在每一折内部重新拟合所有依赖数据的预处理步骤。
> K-fold Cross-validation = 轮流用不同组做 Validation → 每轮重新 Fit Model → 计算并汇总 Validation Loss → 选择合适的模型设置 → 用完整 Development Set 重新训练最终模型。
> 每一折用来验证的数据叫 Validation Set，不是最终的 Test Set。
> 例如：用 4 组（48 个肝脏）训练一个模型。用剩下的 1 组（12 个肝脏）进行 Validation。计算这个模型的 Validation Loss。换一组作为 Validation，再重新训练一个模型。
> 最后取平均的是模型的验证表现（例如 Loss），而不是把 K 个模型本身取平均。

## 模块二：Clustering（聚类分析）？？？
<img width="785" height="507" alt="截屏2026-11-03 10 03 02" src="https://github.com/user-attachments/assets/644cf959-c9cf-4f20-92ee-ae42a27d2330" />
<img width="459" height="278" alt="截屏2026-11-03 10 02 26" src="https://github.com/user-attachments/assets/5fdf30d2-7ada-477c-a306-61881f56bd26" />
<img width="563" height="659" alt="截屏2026-11-03 10 02 06" src="https://github.com/user-attachments/assets/0d686d74-080c-4699-8dee-e11e2232eefa" />

### K-means Clustering

<img width="340" height="627" alt="截屏2026-11-03 10 03 55" src="https://github.com/user-attachments/assets/942bf2ef-7b8e-452a-9665-f9317e1fcd65" />

## 模块三：Logistic Regression（逻辑回归）？？
> [!IMPORTANT]
> Logistic Regression 虽然名字里有 Regression，但通常用于分类问题。
> <img width="667" height="429" alt="截屏2026-11-03 10 47 55" src="https://github.com/user-attachments/assets/32b46187-12b4-4ed2-90c4-60c39580cc72" />

<img width="497" height="665" alt="截屏2026-11-03 10 28 15" src="https://github.com/user-attachments/assets/7a271f93-e51d-463f-a15c-86074d738fab" />
<img width="573" height="633" alt="截屏2026-11-03 10 28 55" src="https://github.com/user-attachments/assets/85142c81-ff07-4a27-8e84-1b90433c18be" />
<img width="360" height="175" alt="截屏2026-11-03 10 29 13" src="https://github.com/user-attachments/assets/5191542b-0a53-4f4b-b6df-d8fdfbb42cc3" />

### Odds
<img width="508" height="625" alt="截屏2026-11-03 10 29 56" src="https://github.com/user-attachments/assets/018cec9c-acbb-4252-a728-2ec9fe2ce719" />
<img width="399" height="586" alt="截屏2026-11-03 10 30 38" src="https://github.com/user-attachments/assets/bbc4a040-1831-491c-9ca9-b91bf0b06870" />
<img width="599" height="652" alt="截屏2026-11-03 10 31 11" src="https://github.com/user-attachments/assets/cb758591-c5b3-41ac-a7b0-dca3b2805a2b" />

待补充

### Likelihood 和 Cross-entropy 这一部分解释：Logistic Regression 到底怎么学习参数？
<img width="424" height="657" alt="截屏2026-11-03 10 34 20" src="https://github.com/user-attachments/assets/496507bd-d722-4acc-82e5-7ddbbe483104" />
<img width="617" height="679" alt="截屏2026-11-03 10 36 23" src="https://github.com/user-attachments/assets/5016c783-edc4-47e1-b6ff-04f1cdb77270" />
<img width="768" height="399" alt="截屏2026-11-03 10 37 29" src="https://github.com/user-attachments/assets/6d643543-d467-446c-b141-0dc94d22cb85" />
<img width="493" height="553" alt="截屏2026-11-03 10 37 50" src="https://github.com/user-attachments/assets/659b52c4-a5df-4993-aebd-5dab463a3da3" />

待补充

### 为什么 Logistic Regression 不稳定？
<img width="604" height="582" alt="截屏2026-11-03 10 45 41" src="https://github.com/user-attachments/assets/46333ad6-fb7d-4e6c-99f0-3d55c905fe63" />
<img width="504" height="447" alt="截屏2026-11-03 10 46 20" src="https://github.com/user-attachments/assets/14ebaeb9-1d80-48b9-89d2-c69f0d3b27cb" />
<img width="584" height="635" alt="截屏2026-11-03 10 52 09" src="https://github.com/user-attachments/assets/8cb6424b-3246-4147-87cf-30b9ce4f180f" />
<img width="462" height="211" alt="截屏2026-11-03 10 52 21" src="https://github.com/user-attachments/assets/482a2301-41bb-41f1-8716-a87986297fbf" />
<img width="641" height="652" alt="截屏2026-11-03 10 51 40" src="https://github.com/user-attachments/assets/43355b63-f3ea-4701-a0e6-47dc4e224684" />

## 模块四：Decision Trees & Random Forest - 一棵树不断问 Yes / No 问题，很多棵树一起做预测。
<img width="572" height="367" alt="截屏2026-11-03 10 54 52" src="https://github.com/user-attachments/assets/6de15ea1-ef3d-4539-bce5-8cc21c511d63" />
<img width="790" height="393" alt="截屏2026-11-03 10 55 19" src="https://github.com/user-attachments/assets/452900ce-3f2c-454a-9a24-26e3dd598e67" />
<img width="593" height="648" alt="截屏2026-11-03 10 55 54" src="https://github.com/user-attachments/assets/d868c92d-9a8a-4f47-9685-89088bf0314f" />
<img width="599" height="665" alt="截屏2026-11-03 10 57 14" src="https://github.com/user-attachments/assets/2955ebfc-d1a6-4564-934d-3a8d389028cb" />
<img width="617" height="418" alt="截屏2026-11-03 10 59 18" src="https://github.com/user-attachments/assets/0dc1300c-f811-4eaa-ac1d-56fe860d2848" />
<img width="641" height="678" alt="截屏2026-11-03 11 00 19" src="https://github.com/user-attachments/assets/cbf56cfe-e0f9-485d-91fb-aec2c9bed8b2" />
<img width="311" height="143" alt="截屏2026-11-03 11 01 20" src="https://github.com/user-attachments/assets/4f622614-8dbd-4bbd-ae7d-790df3aad4a0" />

### Random forest
<img width="715" height="382" alt="截屏2026-11-03 11 02 08" src="https://github.com/user-attachments/assets/850f73f8-9919-4548-bab2-be9b8dd6f285" />
<img width="639" height="618" alt="截屏2026-11-03 11 04 51" src="https://github.com/user-attachments/assets/cbeb2443-391e-49e6-923c-11a66dd73879" />
<img width="456" height="677" alt="截屏2026-11-03 11 06 41" src="https://github.com/user-attachments/assets/cdf37307-6e25-4cf0-ab01-13951282d44a" />
<img width="598" height="674" alt="截屏2026-11-03 11 06 55" src="https://github.com/user-attachments/assets/44a8a796-7710-48ed-a19d-cf1d1e3c0429" />
<img width="418" height="159" alt="截屏2026-11-03 11 07 38" src="https://github.com/user-attachments/assets/f8f0090f-626b-415b-81bd-b342dd7a6c79" />

