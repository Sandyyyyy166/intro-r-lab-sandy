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

