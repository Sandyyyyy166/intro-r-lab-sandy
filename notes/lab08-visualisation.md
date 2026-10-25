# Lab08 Visualisation
<img width="705" height="78" alt="截屏2026-10-20 09 26 30" src="https://github.com/user-attachments/assets/91b212ad-c218-4bc1-a287-08d12e92b876" />

“```{r}”告诉 R Markdown：这不是单纯展示代码，请执行这段 R code
然后你可以 Knit / Render .Rmd，生成带有代码、结果、图表和文字的报告，例如 HTML
更多查询：
```r
?graphics
library(help = "graphics")
```
<img width="746" height="602" alt="截屏2026-10-22 17 57 21" src="https://github.com/user-attachments/assets/e5bd553a-6eb1-44f3-b87e-c92a7519c990" />

## Plotting with R Base
<img width="685" height="294" alt="截屏2026-10-20 09 34 13" src="https://github.com/user-attachments/assets/476bc0b5-89ed-4c59-808c-aaab8bc319c9" />
<img width="557" height="329" alt="截屏2026-10-20 09 34 33" src="https://github.com/user-attachments/assets/856aa7d5-b1b9-49d4-aae9-3e9ea6c5bfec" />  

*折线图*
<img width="341" height="588" alt="截屏2026-10-22 17 46 17" src="https://github.com/user-attachments/assets/08390396-54b4-4503-8bde-b8430bbc8e07" />
<img width="755" height="380" alt="截屏2026-10-22 17 47 06" src="https://github.com/user-attachments/assets/85d8f201-cc65-490a-8d47-b257fb4048aa" />


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

```r
boxplot(y-axis ~ x-axis, Datasets)
```

<img width="631" height="334" alt="截屏2026-10-20 09 40 49" src="https://github.com/user-attachments/assets/a69b0094-508c-4bb0-bb80-a12112c2f316" />

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

> [!TIP]
> plot(out_lv): 画两个图分开

*scatter plot*
```r
plot(
  frogs$rain_mm,
  frogs$calls,
  pch = 19,
  col = "steelblue"
)
```
<img width="398" height="625" alt="截屏2026-10-22 17 48 48" src="https://github.com/user-attachments/assets/3c617d33-8ed1-4cb3-903e-2364968fcf84" />
<img width="470" height="428" alt="截屏2026-10-22 17 51 26" src="https://github.com/user-attachments/assets/aaa76d26-6133-462e-8353-f3a918db7ff8" />  

*histogram*
```r
hist(frogs$calls, breaks = 8) # 叫声数量通常集中在哪个范围？
```

*boxplot*
```r
boxplot(calls ~ weather, data = frogs) # 湿夜和干夜的叫声数量有什么不同？
```

*barchart*
```r
barplot(species$calls,
        names.arg = species$species) # 不同青蛙种类分别记录了多少叫声？
```
**Histogram 用于连续数值的分布；Bar Chart 用于比较不同类别。而 Boxplot 用来比较不同组的数据分布、中位数和离散程度。**


## GGPLOT
<img width="457" height="366" alt="截屏2026-10-20 13 48 58" src="https://github.com/user-attachments/assets/063d0d78-f85b-4060-978a-7f87f16dcc6b" />

<img width="784" height="523" alt="截屏2026-10-20 11 27 00" src="https://github.com/user-attachments/assets/3398cc2a-982f-4fba-b29f-8b9ecc8a50bc" />
<img width="782" height="594" alt="截屏2026-10-20 11 29 13" src="https://github.com/user-attachments/assets/82778a79-5c06-40cf-b729-2526a98cd79b" />

<img width="688" height="351" alt="截屏2026-10-20 09 51 33" src="https://github.com/user-attachments/assets/db880738-07b9-48f4-8700-7484a9f1b855" />
<br>Add lines: 直接 + GEOM_FUNCTION<br>
<img width="417" height="328" alt="截屏2026-10-20 09 52 34" src="https://github.com/user-attachments/assets/a0fd7324-e48e-46b7-b34a-81b0d0f53bd1" />

## 保存PNG
```r
dir.create("png", showWarnings = FALSE)

png_file <- file.path("png", "frog_calls_vs_rain.png")

png(png_file, width = 7, height = 4.5,
    units = "in", res = 150)

plot(frogs$rain_mm, frogs$calls,
     pch = 19, col = "steelblue")

abline(fit, col = "red", lwd = 2)

dev.off()
```
<img width="315" height="644" alt="截屏2026-10-22 17 56 43" src="https://github.com/user-attachments/assets/8c96b156-5109-40b0-b3c2-2dcd9f2c25ce" />

<img width="464" height="565" alt="截屏2026-10-22 18 16 25" src="https://github.com/user-attachments/assets/a331970b-3847-4b37-8bb6-7a9e9dcaae7f" />
<img width="598" height="603" alt="截屏2026-10-22 18 16 44" src="https://github.com/user-attachments/assets/b9eb1468-0b09-4ba3-86ab-b0cb597738ce" />
<img width="476" height="630" alt="截屏2026-10-22 18 17 19" src="https://github.com/user-attachments/assets/bb1d0ab7-d60d-470b-b334-75d23481c545" />
<img width="473" height="645" alt="截屏2026-10-22 18 17 36" src="https://github.com/user-attachments/assets/7e3fb683-a0da-4bba-9838-340c2a7600d5" />
<img width="575" height="587" alt="截屏2026-10-22 18 17 53" src="https://github.com/user-attachments/assets/59bfac9e-dd01-4bbc-a134-0741b30f9834" />
<img width="572" height="606" alt="截屏2026-10-22 18 18 09" src="https://github.com/user-attachments/assets/880bea1d-4e16-4afd-b30b-8bf21e5bb7db" />
<img width="465" height="678" alt="截屏2026-10-22 18 18 24" src="https://github.com/user-attachments/assets/1b4e3adf-9816-455a-b5b1-bfefe8f467da" />
<img width="469" height="586" alt="截屏2026-10-22 18 18 42" src="https://github.com/user-attachments/assets/23e0ecba-18cc-40a5-9987-ebf40a0776f0" />
<img width="710" height="673" alt="截屏2026-10-22 18 19 00" src="https://github.com/user-attachments/assets/55f3e07e-cb85-44f6-b4a0-d3913218fd6b" />
<img width="462" height="548" alt="截屏2026-10-22 18 19 14" src="https://github.com/user-attachments/assets/98e91848-b4b1-442e-b087-d39fef347775" />





