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
xponential Family 不是某一个具体分布，而是一大类可以写成相同数学形式的概率分布。
例如：
- Normal
- Bernoulli
- Binomial
- Poisson
- Gamma
都可以写成指数族形式。

<img width="689" height="314" alt="截屏2026-10-29 10 29 34" src="https://github.com/user-attachments/assets/06b59eeb-d19d-4ce5-b106-0d44efe63bb5" />

## Link function
<img width="607" height="618" alt="截屏2026-10-29 10 31 14" src="https://github.com/user-attachments/assets/97de4117-0e35-465d-a79c-24f920f60178" />
<img width="415" height="603" alt="截屏2026-10-29 10 35 09" src="https://github.com/user-attachments/assets/78c83432-aae7-4b02-9b40-f074bc16314e" />

```r
glm(BP ~ age,
    family = gaussian(link = "identity"),
    data = mydata)
```
<img width="449" height="628" alt="截屏2026-10-29 10 35 34" src="https://github.com/user-attachments/assets/79c30026-88b6-49e3-830f-9c2304223248" />
<img width="527" height="387" alt="截屏2026-10-29 10 36 03" src="https://github.com/user-attachments/assets/8c3826b1-fba5-4780-8ba5-129473a5aaf5" />

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
<img width="477" height="634" alt="截屏2026-10-29 10 38 24" src="https://github.com/user-attachments/assets/c876585b-66ee-437a-ae79-5919b669595d" />
<img width="402" height="96" alt="截屏2026-10-29 10 38 40" src="https://github.com/user-attachments/assets/9d624883-1905-4561-8579-da056d151d93" />

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

<img width="616" height="347" alt="截屏2026-10-29 10 39 15" src="https://github.com/user-attachments/assets/5d84476a-6de7-4809-b444-4a912c7d898b" />
<img width="695" height="327" alt="截屏2026-10-29 10 41 49" src="https://github.com/user-attachments/assets/0855d0c6-4f0e-4a8e-afbb-5db0e0b6e95a" />
<img width="634" height="410" alt="截屏2026-10-29 10 40 07" src="https://github.com/user-attachments/assets/38c5c8fb-bb6e-4afd-ad51-309bc9d1367c" />




