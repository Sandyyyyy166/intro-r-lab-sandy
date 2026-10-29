# 04 Regression
- Exposure: independent variable
- Four key assumptions
• Linearity：residuals as a function of the independent variable -> linear
• Normality：residuals are normally distributed
• Homoscedasticity: 𝜀~𝑁(0, 𝜎^2)
• Independence: all observations are independent of one another
- <img width="652" height="459" alt="截屏2026-10-29 10 24 17" src="https://github.com/user-attachments/assets/1620e90e-8d1b-4068-9e85-e655828b125a" />
- 假设我们研究：
Does age predict systolic blood pressure?
我们建立线性回归：
\[
BP_i=\beta_0+\beta_1 Age_i+\epsilon_i
\]
现在有一个 50 岁的人。
我们可以问两个不同的问题。
Question A：50 岁人群的平均血压是多少？
这对应 Confidence Interval（CI）。
Question B：某个具体 50 岁的人，他的血压可能是多少？
这对应 Prediction Interval（PI）。

## GLM = Generalized Linear Model
我们需要GLM因为：但在 Medical Statistics 中，我们经常遇到：
- 是否死亡：Binary outcome。
- 是否患 malaria：Binary outcome。
- 一年内住院次数：Count outcome。
- Blood pressure：Continuous outcome。
这些数据不一定服从 Normal distribution。
所以 GLM 把普通线性回归推广到了其他分布。
GLMs have the following model components:
• The systematic component
• The random component
• The link function

<img width="446" height="683" alt="截屏2026-10-29 10 28 26" src="https://github.com/user-attachments/assets/036ca86a-54b8-4772-b49e-910fcc2690df" />

## Exponential family
Exponential Family 不是某一个具体分布，而是一大类可以写成相同数学形式的概率分布。
例如：
- Normal
- Bernoulli
- Binomial
- Poisson
- Gamma
都可以写成指数族形式。

<img width="689" height="314" alt="截屏2026-10-29 10 29 34" src="https://github.com/user-attachments/assets/06b59eeb-d19d-4ce5-b106-0d44efe63bb5" />
<img width="679" height="576" alt="截屏2026-10-29 11 11 21" src="https://github.com/user-attachments/assets/7dc6dedd-f77e-45d1-9a13-8fcf1bb9b1d5" />
<img width="628" height="455" alt="截屏2026-10-29 11 11 37" src="https://github.com/user-attachments/assets/2d755fc3-dbab-4ed8-af62-1d44ef60bdc7" />


## Link function
<img width="546" height="622" alt="截屏2026-10-29 11 01 53" src="https://github.com/user-attachments/assets/ed8e357e-8fe6-4bf5-8c90-6f6a3591ad75" />
<img width="505" height="215" alt="截屏2026-10-29 11 03 00" src="https://github.com/user-attachments/assets/0a8c9734-d4a9-492d-9164-a742e4d885d1" />
<img width="607" height="618" alt="截屏2026-10-29 10 31 14" src="https://github.com/user-attachments/assets/97de4117-0e35-465d-a79c-24f920f60178" />
<img width="616" height="347" alt="截屏2026-10-29 10 39 15" src="https://github.com/user-attachments/assets/5d84476a-6de7-4809-b444-4a912c7d898b" />
<img width="695" height="327" alt="截屏2026-10-29 10 41 49" src="https://github.com/user-attachments/assets/0855d0c6-4f0e-4a8e-afbb-5db0e0b6e95a" />
<img width="634" height="410" alt="截屏2026-10-29 10 40 07" src="https://github.com/user-attachments/assets/38c5c8fb-bb6e-4afd-ad51-309bc9d1367c" />
<img width="691" height="666" alt="截屏2026-10-29 11 04 47" src="https://github.com/user-attachments/assets/ff6e43d5-8878-4b15-8af6-35a56251902b" />


## Normal regression
<img width="415" height="603" alt="截屏2026-10-29 10 35 09" src="https://github.com/user-attachments/assets/78c83432-aae7-4b02-9b40-f074bc16314e" />
<img width="535" height="682" alt="截屏2026-10-29 11 07 57" src="https://github.com/user-attachments/assets/3195f34a-1e23-476d-904a-9526f5a1b7ac" />
<img width="387" height="319" alt="截屏2026-10-29 11 08 14" src="https://github.com/user-attachments/assets/c57c5fa8-2083-4939-9652-fcd2541fdbc3" />

```r
glm(BP ~ age,
    family = gaussian(link = "identity"),
    data = mydata)
```

## Logistic regression
<img width="712" height="153" alt="截屏2026-10-29 10 54 15" src="https://github.com/user-attachments/assets/cf5949e4-00c6-4eb1-834e-c0eff191badf" />
<img width="669" height="210" alt="截屏2026-10-29 10 54 36" src="https://github.com/user-attachments/assets/aa94f9cb-a4f2-408a-8b4a-e4e135d6391f" />
<img width="449" height="628" alt="截屏2026-10-29 10 35 34" src="https://github.com/user-attachments/assets/79c30026-88b6-49e3-830f-9c2304223248" />
<img width="527" height="387" alt="截屏2026-10-29 10 36 03" src="https://github.com/user-attachments/assets/8c3826b1-fba5-4780-8ba5-129473a5aaf5" />
<img width="453" height="619" alt="截屏2026-10-29 11 09 01" src="https://github.com/user-attachments/assets/9a511933-bc43-4275-a785-069e85e06d75" />
<img width="431" height="610" alt="截屏2026-10-29 11 09 13" src="https://github.com/user-attachments/assets/9dad9501-2922-4932-8c9f-fd0e79537059" />
<img width="419" height="366" alt="截屏2026-10-29 11 09 29" src="https://github.com/user-attachments/assets/dedb8d8f-3cc6-49a3-9d45-a9c7a4058523" />
<img width="679" height="586" alt="截屏2026-10-29 11 09 41" src="https://github.com/user-attachments/assets/426777df-6aea-4d4d-8c92-8c117120edf7" />
<img width="430" height="380" alt="截屏2026-10-29 11 09 59" src="https://github.com/user-attachments/assets/4ecaf48b-9ce2-4567-954f-a7a8408ada33" />

```r
model <- glm(
  death ~ treatment + age,
  family = binomial(link = "logit"),
  data = mydata
)

summary(model)

# Odds ratios
exp(coef(model))
```

## Poisson regression
<img width="477" height="634" alt="截屏2026-10-29 10 38 24" src="https://github.com/user-attachments/assets/c876585b-66ee-437a-ae79-5919b669595d" />
<img width="402" height="96" alt="截屏2026-10-29 10 38 40" src="https://github.com/user-attachments/assets/9d624883-1905-4561-8579-da056d151d93" />
<img width="447" height="660" alt="截屏2026-10-29 11 10 28" src="https://github.com/user-attachments/assets/5ec24815-c6de-4eb9-8c05-140b6a449534" />
<img width="554" height="545" alt="截屏2026-10-29 11 10 39" src="https://github.com/user-attachments/assets/49f73dda-40d1-4642-bdaf-8c9f0fb8f967" />

```r
model <- glm(
  n_hosp ~ treatment + offset(log(person_time)),
  family = poisson(link = "log"),
  data = mydata
)

summary(model)

# Incidence rate ratios
exp(coef(model))
```

## MLE
<img width="574" height="326" alt="截屏2026-10-29 11 12 58" src="https://github.com/user-attachments/assets/15f0595b-b5b3-4f00-8980-f6a140709432" />
<img width="662" height="316" alt="截屏2026-10-29 11 13 24" src="https://github.com/user-attachments/assets/2e9be120-a9b0-4470-8793-8aa35084b2cb" />
<img width="662" height="253" alt="截屏2026-10-29 11 13 43" src="https://github.com/user-attachments/assets/20baf56c-ccf3-477c-b49f-67146a7f232f" />
<img width="618" height="279" alt="截屏2026-10-29 11 13 59" src="https://github.com/user-attachments/assets/5ab85bd1-5ca8-4dd7-8cf8-5061eef00666" />
<img width="672" height="351" alt="截屏2026-10-29 11 14 50" src="https://github.com/user-attachments/assets/f31eb695-87ce-4214-82dc-cd97779b634c" />

## Likelihood ratio test - 比较两个模型，看更复杂的模型是否比简单模型显著更好地解释数据
<img width="432" height="647" alt="截屏2026-10-29 13 10 46" src="https://github.com/user-attachments/assets/407b10e9-33ee-4699-a181-643e0cfa3dde" />
<img width="467" height="462" alt="截屏2026-10-29 13 12 39" src="https://github.com/user-attachments/assets/54551b84-9810-44fc-8d33-0e96e1c2c166" />
```r
# Reduced model
model0 <- glm(
  death ~ age,
  family = binomial,
  data = study_data
)

# Full model
model1 <- glm(
  death ~ age + sex,
  family = binomial,
  data = study_data
)

# Likelihood Ratio Test
anova(model0, model1, test = "Chisq")
```
