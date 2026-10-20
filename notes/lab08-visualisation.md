# Lab08 Visualisation
<img width="705" height="78" alt="截屏2026-10-20 09 26 30" src="https://github.com/user-attachments/assets/91b212ad-c218-4bc1-a287-08d12e92b876" />
“```{r}”告诉 R Markdown：这不是单纯展示代码，请执行这段 R code
然后你可以 Knit / Render .Rmd，生成带有代码、结果、图表和文字的报告，例如 HTML
更多查询：
```r
?graphics
library(help = "graphics")
```
## Plotting with R Base
<img width="685" height="294" alt="截屏2026-10-20 09 34 13" src="https://github.com/user-attachments/assets/476bc0b5-89ed-4c59-808c-aaab8bc319c9" />
<img width="557" height="329" alt="截屏2026-10-20 09 34 33" src="https://github.com/user-attachments/assets/856aa7d5-b1b9-49d4-aae9-3e9ea6c5bfec" />
<img width="365" height="328" alt="截屏2026-10-20 09 36 13" src="https://github.com/user-attachments/assets/11012fec-110e-45c4-80db-f90b96520496" />
plot(x, y): 用 x 当横坐标，y 当纵坐标 -- R 会把对应位置配成坐标
(1,2)
(2,5)
(3,4)
plot(4:9)只有一个 vector，没有提供 x, 这时候 R 自动使用 index（位置） 当作 x
index (x)    value (y)
1            4
2            5
3            6
4            7
5            8
6            9
<img width="681" height="331" alt="截屏2026-10-20 09 35 55" src="https://github.com/user-attachments/assets/1ad53aa3-953b-4f0d-adbb-3aaeeaab35fe" />
"pch": solidity of a point 点的深度
<img width="544" height="340" alt="截屏2026-10-20 09 38 00" src="https://github.com/user-attachments/assets/df9afcf8-dd46-424f-a080-27b918766160" />
<img width="650" height="316" alt="截屏2026-10-20 09 38 17" src="https://github.com/user-attachments/assets/d6139381-f074-4d93-9bee-df1217876e62" />
```r
boxplot(y-axis ~ x-axis, Datasets)
```
<img width="631" height="334" alt="截屏2026-10-20 09 40 49" src="https://github.com/user-attachments/assets/a69b0094-508c-4bb0-bb80-a12112c2f316" />
<img width="688" height="351" alt="截屏2026-10-20 09 51 33" src="https://github.com/user-attachments/assets/db880738-07b9-48f4-8700-7484a9f1b855" />
Add lines: 直接 + GEOM_FUNCTION
<img width="417" height="328" alt="截屏2026-10-20 09 52 34" src="https://github.com/user-attachments/assets/a0fd7324-e48e-46b7-b34a-81b0d0f53bd1" />



