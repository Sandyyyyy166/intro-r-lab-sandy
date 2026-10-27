# 02 Hypothesis Testing 27/10/2026
**Test Statistic**: A statistic used to make a test
<img width="363" height="287" alt="截屏2026-10-27 09 31 50" src="https://github.com/user-attachments/assets/2da3fdb1-533e-4e1b-90ce-607af101cc69" />

**Summary Statistic**: A statistic used to make a summary, e.g., sample mean

Remember:
• Not statistically significant ¹ no clinical difference

• Statistically significant ¹ important

• P-values depend on the sample size

• P-values give no information regarding direction or magnitude of effect

## Errors
<img width="556" height="356" alt="截屏2026-10-27 09 41 09" src="https://github.com/user-attachments/assets/e7c0586e-c8f6-45f3-8fd6-9734731d63c4" />

**Type I error (significance level of a test)**
• We reject the null hypothesis although the null hypothesis is true

• The probability of type I error is the significance level, written as α

**Type II error (related to the power of a test)**
• We fail to reject the null hypothesis although the null hypothesis is false

• The probability of type II error is written as β

• Power is defined as 1-β

*Statistical power:* 
“What’s the probability we detect a difference, given there is a difference?”
**图示**
• 黄色区域：这个时候H1是对的，但是我们得出的β要reject H1

• 绿色区域：这个时候H0是对的，但是我们得出的α要reject H0

• 虚线：critical value告诉我们rejection region在哪
<img width="360" height="216" alt="截屏2026-10-27 09 48 36" src="https://github.com/user-attachments/assets/ecbd23e7-3233-49a6-b77f-36dcb187dbb6" />

## Comparison of two proportions -> Chi squared
<img width="642" height="357" alt="截屏2026-10-27 09 51 30" src="https://github.com/user-attachments/assets/d474b886-e44d-4062-9417-392fb92ea9ca" />

红线：critical value告诉我们rejection region在哪
<img width="321" height="210" alt="截屏2026-10-27 09 59 24" src="https://github.com/user-attachments/assets/e6505c93-98d8-4a81-8c66-6ffde1e86cb6" />

## Comparison of two means -> student t test
<img width="626" height="285" alt="截屏2026-10-27 10 02 03" src="https://github.com/user-attachments/assets/51d982d8-e902-44aa-8461-15a5fbf89fbc" />

• Can be used for small samples and large samples

• Assumes that population distributions are normal and the population standard deviation is the same in the two groups

• May not be appropriate to use when the sample standard deviations (s1, s2) are very different

## Paired t-test
<img width="587" height="326" alt="截屏2026-10-27 10 14 21" src="https://github.com/user-attachments/assets/c2d863e6-aafa-4fcd-88c0-9b9fbaa5d608" />

## Measure outcome
<img width="792" height="358" alt="截屏2026-10-27 10 58 23" src="https://github.com/user-attachments/assets/84b0630c-04f3-4407-95da-e69efcf30d63" />

### Odds: 
Probability of an event occurring divided by the probability that the event does not happen

### Risk & cumulative incidence：
**Incidence**
— Incidence is a measure of occurrence of events (i.e., state transition from a non-diseased to a diseased state)

— Therefore a measure of risk and can be expressed either as a risk (cumulative
incidence) or a rate
<img width="713" height="353" alt="截屏2026-10-27 10 56 48" src="https://github.com/user-attachments/assets/4a93c6fe-6584-43c8-9436-dce622e4c713" />
<img width="741" height="358" alt="截屏2026-10-27 11 02 44" src="https://github.com/user-attachments/assets/a5176a4b-b0c4-4fa4-bfd4-fd3d748adead" />

> [!TIP]
> 为什么Incidence 可以是 Risk，也可以是 Rate
> 
> <img width="605" height="572" alt="截屏2026-10-27 11 28 08" src="https://github.com/user-attachments/assets/8047ac92-8c56-470d-b445-1d704d639fcd" />
> <img width="661" height="660" alt="截屏2026-10-27 11 28 46" src="https://github.com/user-attachments/assets/5b14bc6c-ecc6-45d4-96f9-30f6966bb3b4" />

Incidence rate: 95% confidence interval
95% CI: Estimate ± 1.96 × SE

<img width="609" height="304" alt="截屏2026-10-27 11 08 01" src="https://github.com/user-attachments/assets/768581b2-9126-4960-9568-853c2067252a" />
<img width="525" height="279" alt="截屏2026-10-27 11 08 17" src="https://github.com/user-attachments/assets/9ac80885-9321-4244-9fd4-990c68110074" />

### Prevalence
— What proportion (fraction/percentage) of the population is affected by the disease
<img width="581" height="289" alt="截屏2026-10-27 11 11 15" src="https://github.com/user-attachments/assets/8f071b87-8625-4c12-9368-7785da9537c4" />
- Prevalence is not a measure of risk

> [!TIP]
> Incidence = 有多少人新得病？
> Prevalence = 现在有多少人患病？
> NEW cases vs EXISTING cases
> 
> <img width="753" height="685" alt="截屏2026-10-27 11 24 57" src="https://github.com/user-attachments/assets/b8eea1ee-346a-4692-bbd5-71f9e653db82" />
> <img width="496" height="395" alt="截屏2026-10-27 11 26 20" src="https://github.com/user-attachments/assets/888eb2fb-ba75-4595-b95a-ee67f7e83270" />
> <img width="598" height="508" alt="截屏2026-10-27 11 26 41" src="https://github.com/user-attachments/assets/1eb1b9cb-c46d-46bc-978d-723feb17ad81" />
> 两者关系
> <img width="605" height="488" alt="截屏2026-10-27 11 29 44" src="https://github.com/user-attachments/assets/3ca12825-cd70-47f1-a656-b338e20fffb2" />
> Incidence = 流进水池的水，代表新发病例。
> Prevalence = 水池里现有的水，代表当前患病人数。
> Recovery / Death = 流出去的水，代表患者离开患病状态。
> 所以Prevalence 不只取决于有多少人新患病，还取决于患者在患病状态中停留多久。
> <img width="530" height="662" alt="截屏2026-10-27 11 31 39" src="https://github.com/user-attachments/assets/bd2e2af9-71d8-4e98-8ead-af4c58c6f810" />

> [!IMPORTANT]
> <img width="625" height="488" alt="截屏2026-10-27 11 34 48" src="https://github.com/user-attachments/assets/b9fd7d65-10fa-413e-94e8-2775d7b94995" />
> <img width="645" height="270" alt="截屏2026-10-27 14 09 26" src="https://github.com/user-attachments/assets/0ffa03c6-759a-410f-9468-18d620855670" />
> <img width="635" height="339" alt="截屏2026-10-27 14 22 56" src="https://github.com/user-attachments/assets/ade7eea4-b7ff-4ffb-b42a-bf0dbf8e48f2" />
> **公示表**
> <img width="679" height="443" alt="截屏2026-10-27 14 33 31" src="https://github.com/user-attachments/assets/0f26ffc9-6393-4169-aba5-e17def5c12e4" />
> <img width="577" height="615" alt="截屏2026-10-27 14 33 53" src="https://github.com/user-attachments/assets/a2db39bf-4b2a-4a81-93fa-9d11fe376a08" />

*Exercise*

<img width="631" height="668" alt="截屏2026-10-27 11 33 04" src="https://github.com/user-attachments/assets/2d0e3ad7-949d-40d6-95af-65446413cffa" />
<img width="631" height="665" alt="截屏2026-10-27 11 33 39" src="https://github.com/user-attachments/assets/ab5066db-e165-45cc-8daa-3f040aa9a29a" />
<img width="744" height="585" alt="截屏2026-10-27 11 34 22" src="https://github.com/user-attachments/assets/508c665b-e46d-4e02-9860-595efa8d61c4" />

## Effect measures
<img width="659" height="313" alt="截屏2026-10-27 11 56 22" src="https://github.com/user-attachments/assets/60f80e8f-ccb5-4509-a440-efdadd33bf79" />

### Risk ratio
<img width="635" height="349" alt="截屏2026-10-27 11 56 49" src="https://github.com/user-attachments/assets/b7fb85d9-0358-4d99-9faf-da385da5b8f4" />
<img width="582" height="279" alt="截屏2026-10-27 11 57 03" src="https://github.com/user-attachments/assets/d7bfbece-8622-4f4e-b7e1-63a4c54aeb92" />
<img width="546" height="123" alt="截屏2026-10-27 11 57 17" src="https://github.com/user-attachments/assets/ca9c5c5d-3ebf-49f5-9e1b-f0cc2320dfa1" />
risk at exposed / risk at unexposed
= incidence at exposed / incidence at unexposed
= (84/3000) / (87/5000)

> [!NOTE]
> 记住公式a/(a+b), c/(c+d)是分子除以total！和not那一部分没有关系

### Risk difference
<img width="442" height="301" alt="截屏2026-10-27 12 00 07" src="https://github.com/user-attachments/assets/a7f4b2f5-36a2-4eec-9832-d095d3e2f42c" />
<img width="635" height="236" alt="截屏2026-10-27 12 00 22" src="https://github.com/user-attachments/assets/b0929444-e83d-4752-9c39-0b8f76088857" />

所以上个例子就应该是(84/3000) - (87/5000)

> [!IMPORTANT]
> 第一个例题
> Prevalence：在某个时间点，有多少活着的人正在患病？
> Cumulative incidence：在一段时间内，最初未患病的人中有多少新发病例？
> Person-time：每个人贡献了多少尚未患病、仍处于风险中的时间？
> Incidence rate：每单位 person-time 发生多少新病例？
> 
> <img width="454" height="320" alt="截屏2026-10-27 13 54 14" src="https://github.com/user-attachments/assets/e69ee127-d51c-492d-a677-2a6c89b899f2" />
> <img width="540" height="536" alt="截屏2026-10-27 13 58 59" src="https://github.com/user-attachments/assets/0243bcd7-2b72-45e6-95ee-282a6a652900" />
> <img width="570" height="523" alt="截屏2026-10-27 13 59 15" src="https://github.com/user-attachments/assets/5a663a95-3a4e-44e1-b687-3644e7e030f1" />
> <img width="746" height="628" alt="截屏2026-10-27 13 59 34" src="https://github.com/user-attachments/assets/6c07120a-8914-45fe-a8df-88c8bad0f167" />
> <img width="777" height="614" alt="截屏2026-10-27 14 02 37" src="https://github.com/user-attachments/assets/46a430ac-f728-4e2c-a420-c847799363b5" />
> <img width="584" height="647" alt="截屏2026-10-27 14 03 54" src="https://github.com/user-attachments/assets/3bd08cca-d5a6-432a-96ff-920e7bee07c1" />
> <img width="662" height="573" alt="截屏2026-10-27 14 05 09" src="https://github.com/user-attachments/assets/377dd7a8-97d9-4102-9855-de958975e0e6" />

### Odds ratio
<img width="614" height="274" alt="截屏2026-10-27 13 10 11" src="https://github.com/user-attachments/assets/8ee12c8d-10a4-4adf-816b-e5ca17c35df6" />

> [!NOTE]
> 和risk ratio的区别就是分母是no death那一列，不是total了
> 
> <img width="492" height="174" alt="截屏2026-10-27 13 21 04" src="https://github.com/user-attachments/assets/1d45cc47-46e4-4489-8fa7-a9e11fe6dd9a" />
> <img width="781" height="587" alt="截屏2026-10-27 13 37 06" src="https://github.com/user-attachments/assets/fccf99ef-a854-410b-8876-a6add7517aa1" />
> <img width="463" height="669" alt="截屏2026-10-27 13 40 29" src="https://github.com/user-attachments/assets/b5eb8ef1-71a3-4e11-8224-edddd6197073" />
> <img width="461" height="583" alt="截屏2026-10-27 13 41 06" src="https://github.com/user-attachments/assets/21ca3ec7-707f-4a0b-8749-ba83b3105b52" />

> [!IMPORTANT]
> 第二个例题
> <img width="617" height="357" alt="截屏2026-10-27 14 26 48" src="https://github.com/user-attachments/assets/b940af49-c02d-4cbc-9fa6-e7f214e15cb8" />
> <img width="736" height="603" alt="截屏2026-10-27 14 27 24" src="https://github.com/user-attachments/assets/1d94a578-e773-4b7a-8c52-fa33a69e1f68" />
> <img width="789" height="515" alt="截屏2026-10-27 14 27 43" src="https://github.com/user-attachments/assets/5c24c84d-e931-4b1b-85ba-16697733a14e" />
> <img width="488" height="511" alt="截屏2026-10-27 14 28 18" src="https://github.com/user-attachments/assets/19523f59-2155-465e-8a4c-df01275eca1c" />
> <img width="486" height="669" alt="截屏2026-10-27 14 28 55" src="https://github.com/user-attachments/assets/9d31aafa-c092-458c-845d-c9abec63ad2e" />
> <img width="522" height="670" alt="截屏2026-10-27 14 31 32" src="https://github.com/user-attachments/assets/b8012bbb-f65a-4292-a8cc-2c70e9a490f4" />
> <img width="440" height="634" alt="截屏2026-10-27 14 32 07" src="https://github.com/user-attachments/assets/4939c50d-370a-4439-960a-9ce0b55d0743" />
> <img width="482" height="470" alt="截屏2026-10-27 14 32 27" src="https://github.com/user-attachments/assets/51497897-09df-45fd-bcf0-00c9279b1ec0" />



















