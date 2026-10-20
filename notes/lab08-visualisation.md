# Lab08 Visualisation
<img width="705" height="78" alt="截屏2026-10-20 09 26 30" src="https://github.com/user-attachments/assets/91b212ad-c218-4bc1-a287-08d12e92b876" />
<br>“```{r}”告诉 R Markdown：这不是单纯展示代码，请执行这段 R code
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
<br>plot(x, y): 用 x 当横坐标，y 当纵坐标 -- R 会把对应位置配成坐标
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
<br>
<img width="681" height="331" alt="截屏2026-10-20 09 35 55" src="https://github.com/user-attachments/assets/1ad53aa3-953b-4f0d-adbb-3aaeeaab35fe" />
"pch": solidity of a point 点的深度
<img width="544" height="340" alt="截屏2026-10-20 09 38 00" src="https://github.com/user-attachments/assets/df9afcf8-dd46-424f-a080-27b918766160" />
<img width="650" height="316" alt="截屏2026-10-20 09 38 17" src="https://github.com/user-attachments/assets/d6139381-f074-4d93-9bee-df1217876e62" />
<br>
```r
boxplot(y-axis ~ x-axis, Datasets)
```
<br>
<img width="631" height="334" alt="截屏2026-10-20 09 40 49" src="https://github.com/user-attachments/assets/a69b0094-508c-4bb0-bb80-a12112c2f316" />
<br>
R会算sin(1), sin(2), sin(3), ... sin(10)
然后它创建了三个vector：
sin(1:10) * 0.1
sin(1:10) * 3
sin(1:10) * 1.8
不同的高度的波
cbind = column bind，把三个 vector 按列拼成一个 matrix
          [,1]       [,2]       [,3]

1      sin(1)*0.1  sin(1)*3   sin(1)*1.8
2      sin(2)*0.1  sin(2)*3   sin(2)*1.8
3      sin(3)*0.1  sin(3)*3   sin(3)*1.8
...
10     sin(10)*0.1 sin(10)*3  sin(10)*1.8
matplot(...)把 matrix 的每一列分别画出来
type = "l"
  "l" = line，所以画线，而不是只画点
lty = 1
  lty = line type，1 是普通实线
col = c("red", "blue", "black")设置颜色
legend() 就是添加右上角那个图例
"topright" = 放右上角
<br>
## GGPLOT
<img width="784" height="523" alt="截屏2026-10-20 11 27 00" src="https://github.com/user-attachments/assets/3398cc2a-982f-4fba-b29f-8b9ecc8a50bc" />
<img width="782" height="594" alt="截屏2026-10-20 11 29 13" src="https://github.com/user-attachments/assets/82778a79-5c06-40cf-b729-2526a98cd79b" />



<img width="688" height="351" alt="截屏2026-10-20 09 51 33" src="https://github.com/user-attachments/assets/db880738-07b9-48f4-8700-7484a9f1b855" />
<br>Add lines: 直接 + GEOM_FUNCTION<br>
<img width="417" height="328" alt="截屏2026-10-20 09 52 34" src="https://github.com/user-attachments/assets/a0fd7324-e48e-46b7-b34a-81b0d0f53bd1" />



