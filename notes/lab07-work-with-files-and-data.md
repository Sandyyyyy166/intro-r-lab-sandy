# Lab 07 Work with files and data
## csv
CSV 文件   
   ↓   
read.csv()   
   ↓   
Data Frame  
   ↓   
先检查数据  
   ↓  
发现 NA / 检查结构  
   ↓   
计算  
   ↓   
筛选 subset()   
   ↓   
分组 aggregate()   
   ↓  
增加新 column  
   ↓  
merge 两张表   
   ↓  
write.csv() 保存结果,把结果存回硬盘,R → CSV

<img width="418" height="481" alt="截屏2026-10-22 15 43 49" src="https://github.com/user-attachments/assets/b7758b2a-ea68-46ee-b36c-6189f680af6f" />

CSV = Comma-Separated Values 逗号分隔值文件 本质上其实只是一个纯文本文件。  
每一行 = 一条 observation。每个逗号 = 分隔不同 column。  
Excel 可以打开 CSV，但 CSV 本身不是 Excel 文件。

```r
sightings <- read.csv("data/sightings.csv")
```
右：= 找到这个 CSV → 读取它 → 转成 data frame。  
左：= 把得到的 data frame 保存到 sightings。
```r
read.csv("data/sightings.csv") # 相对路径
```
实际理解成：/Users/wuyu/r_work/intro-r-lab-07/data/sightings.csv  

## 读数据
```r
head(sightings) # 默认显示前 6 行 - head() = 偷看数据顶部。
str(sightings) # 看数据结构 - 这是 data frame 吗？几行几列？column 名叫什么？每个 column 是什么 type？
summary(weather) # Min.;1st Qu.;Median;Mean;3rd Qu.;Max.;NA's;找NA
nrow(sightings) # = number of rows
ncol(sightings) # = number of columns
sightings$count # 从 sightings 这张表里，把 count 这一列拿出来
sum(sightings$count)
mean(weather$temp_c)
```

## subset()
```r
canopy <- subset(sightings, site == "Canopy") # 只留下 TRUE 的 rows
```

## == comparison
`x == 5` 是在问：x 等于 5 吗？

## aggregate 按照某个类别分组（group），然后对每一组分别进行计算
FUN可以根据研究问题，换成不同函数，比如mean/max/min/length
<img width="755" height="530" alt="截屏2026-10-22 15 37 04" src="https://github.com/user-attachments/assets/2ec7df6c-31a1-4697-858b-1e1ee5dc5091" />
<img width="756" height="672" alt="截屏2026-10-22 15 37 41" src="https://github.com/user-attachments/assets/6fbb1f1d-16f6-4375-b388-c2f9fa9b37ce" />

## 给data frame加column
<img width="763" height="658" alt="截屏2026-10-22 15 41 45" src="https://github.com/user-attachments/assets/ec22b726-e98e-4a76-95ae-69467d5142e5" />
<img width="749" height="678" alt="截屏2026-10-22 15 42 03" src="https://github.com/user-attachments/assets/5b8c1183-d546-4dee-9cae-05043f0b5e7b" />

## merge()
```r
merge(
    sightings,
    weather,
    by = c("date", "site") # 把当天、那个 site 的天气放到对应的 sighting 旁边
)
merged <- merge(
    table1,
    table2,
    by = c("date", "site")
)
```

## NA and NULL
NA: missing data
```r
c(1, 2, 3)[4]
a <- c(1, 2, 3)
length(a) <- 100
print(a)
```
NULL: undefined computing object
```r
f <- function(){}
a <- f() # because this function does not return anything
a

x <- c("a" = 1, "b" = 2, "c" = 3)
# 得到a b c 为name attributes
#    1 2 3
# remove the names attribute of x
names(x) <- NULL
x
# [1] 1 2 3

v1 <- c(1, 2, 3)
# v2 <- NULL # same as v2 <- c()
for (ii in 1:10) {
v2 <- c(v2,v1)
}
```
开始
v2 = NULL
第1次
v2 = 1 2 3
第2次
v2 = 1 2 3 1 2 3
第3次
v2 = 1 2 3 1 2 3 1 2 3
...
第10次
v2 = 1 2 3 1 2 3 ... 1 2 3

> [!TIP]
> NA 的意思不是某个具体的值，而是 “I don't know / missing”
```r
is.na(NA) # TRUE 这个东西是不是 missing value？
any(is.na(c(1:10, NA))) # TRUE 解释见下面
```
c(1:10, NA)得到1 2 3 4 5 6 7 8 9 10 NA
is.na(c(1:10, NA))相当于FALSE FALSE FALSE ... FALSE TRUE
any(...)问的是：这里面有没有至少一个 TRUE？所以是TRUE

```r
na.rm = TRUE # NA remove 比如sum(rain, na.rm = TRUE)
```

<img width="782" height="628" alt="截屏2026-10-19 13 45 16" src="https://github.com/user-attachments/assets/7f975365-f215-4012-bfb7-33e6fd86c9be" />
<img width="782" height="648" alt="截屏2026-10-19 13 45 37" src="https://github.com/user-attachments/assets/5b4e9c41-50d8-41f8-a774-ca811d10f2cd" />
<img width="787" height="611" alt="截屏2026-10-19 13 46 05" src="https://github.com/user-attachments/assets/5b5c2d83-eef6-4490-8cf8-c8026fcdcb2d" />
<img width="794" height="561" alt="截屏2026-10-19 13 46 28" src="https://github.com/user-attachments/assets/c818b2d5-466e-426e-b4d1-84808b54bdd3" />
<img width="803" height="512" alt="截屏2026-10-19 13 48 37" src="https://github.com/user-attachments/assets/3381f3dd-97d2-44e9-aed4-67e14c487237" />
<img width="781" height="457" alt="截屏2026-10-19 13 48 56" src="https://github.com/user-attachments/assets/acda9989-9f30-4a03-adb1-f405f27a635a" />
<img width="781" height="568" alt="截屏2026-10-19 13 49 17" src="https://github.com/user-attachments/assets/6578860b-0617-4b2e-ac64-dfe1204801af" />
<img width="775" height="641" alt="截屏2026-10-19 13 49 33" src="https://github.com/user-attachments/assets/4d56aeeb-e157-4fce-908f-ecc5e97e1bbd" />
<img width="783" height="526" alt="截屏2026-10-19 13 50 04" src="https://github.com/user-attachments/assets/228f76ca-cab8-46fd-9d09-6b3357350b11" />
<img width="776" height="558" alt="截屏2026-10-19 13 50 39" src="https://github.com/user-attachments/assets/fe5317d5-98d8-4684-b242-9e966185ab50" />
<img width="789" height="581" alt="截屏2026-10-19 13 51 07" src="https://github.com/user-attachments/assets/ddf76cb0-e125-4892-8bc8-94f29a0ac91c" />
<img width="794" height="507" alt="截屏2026-10-19 13 51 26" src="https://github.com/user-attachments/assets/9d97a19a-f167-4371-b7a5-2d69e54bc2e8" />
<img width="783" height="615" alt="截屏2026-10-19 13 51 44" src="https://github.com/user-attachments/assets/251e743d-b9dd-4424-b822-5ea2986291ab" />
<img width="779" height="618" alt="截屏2026-10-19 13 52 01" src="https://github.com/user-attachments/assets/a0415361-2b20-466e-a16c-5772cdfb42f2" />
<img width="790" height="524" alt="截屏2026-10-19 13 52 36" src="https://github.com/user-attachments/assets/f437f237-6704-4bcb-b7c6-001186bb3293" />
<img width="785" height="355" alt="截屏2026-10-19 13 52 51" src="https://github.com/user-attachments/assets/b9e205f7-4d78-4dc6-a9ab-695ab6338866" />
<img width="643" height="519" alt="截屏2026-10-19 13 53 11" src="https://github.com/user-attachments/assets/865fcc55-9036-418c-925b-fb4f8bb6d8d9" />












