# Lab05 Modelling Random Events
```r
runif(5) # 随机生成 5 个介于 0 和 1 之间的数字

rand_numbs <- runif(5)
sprouted <- rand_numbs < 0.7
# 把“概率”转化成了一次具体实验结果,obtain logical vector, TRUE/FALSE因为comparison（比较）本质上是在问 R 一个“是/否问题”比如
rolls <- c(0.2, 0.9, 0.5, 0.4)
rolls < 0.7 # TRUE FALSE TRUE TRUE
sum(sprouted) # 数 TRUE

which(sprouted) # 找 TRUE 的位置 [1]1 3 5 TRUE 出现在第 1、3、5 个位置

set.seed(5)
# Reproducibility 从编号 5 的固定起点开始生成随机序列, 固定随机结果
n_sprouts_per_tray <- rep(0, n_trays) # repeat n times so 0 0 0 n个0 建空vector
numeric(5) # 也是0 0 0 0 0

for (ii in 1:n_trays) { # loop 决定现在处理第几盘
    rand_numbs <- runif(n_seeds_per_tray)
    sprouted <- rand_numbs < p_sprout
    n_sprouts_per_tray[ii] <- sum(sprouted) # [ii] 决定把结果存到第几个位置
} # 每一次 loop 都模拟一整盘 100 颗种子

mean(n_sprouts_per_tray)
min(n_sprouts_per_tray)
max(n_sprouts_per_tray)
hist(n_sprouts_per_tray) # 画直方图
quantile(
    n_sprouts_per_tray,
    c(0.05, 0.95)
)
# 5%   95%
# 62    77 中间 90% 的结果大概落在 62～77 颗之间
```
所以这个事件的逻辑：
Probability 0.7
      ↓
runif() 产生随机数
      ↓
< 0.7
      ↓
TRUE / FALSE
      ↓
sum() 数发芽颗数
      ↓
for loop 重复 1000 次
      ↓
vector 保存 1000 个结果
      ↓
mean / min / max / quantile / hist
      ↓
看出随机事件的整体规律

> [!IMPORTANT]
> 我们约定从同一个起点开始读这串随机数, set.seed() 不是“让数字不随机”, 而是：让随机实验可以被重复（reproducible）
```r
set.seed(5)
runif(3)
set.seed(5)
runif(3)
```

> 但是下面这种情况不适用，一个set.seed的话
```r
set.seed(5)

runif(3)
runif(3)
```
set.seed(5)
     ↓
   起点
     ↓
0.20 0.68 0.92 0.28 0.10 0.70 ...
 ↑    ↑    ↑
 第一次 runif(3)

               ↑    ↑    ↑
               第二次 runif(3)


