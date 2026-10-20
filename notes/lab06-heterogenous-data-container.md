# Lab06 Heterogenous Data Container
Vector 要求里面的数据是同一种类型；
```r
temperatures <- c(18, 20, 19, 21)
```
List 可以把不同类型、不同长度的东西装在一起
  尤其是要把character和numeric放在一起的时候不然比如用vector的话用sum()会报错，因为已经强制转化为character
  想成一个大盒子，里面又装着几个不同的小盒子————不同东西的收纳箱
```r
experiment <- list(
    temperatures = c(18, 20, 19, 21),
    researcher = "Maya",
    successful = TRUE
)
```
Data frame 是一种特殊的 list
```r
weather <- data.frame(
    day = c("Mon", "Tue", "Wed"),
    temperature = c(18, 20, 19),
    raining = c(TRUE, FALSE, TRUE)
)
```
Atomic vector = 一排同一种 type 的数据

## str(): 可以理解成 structure，查找内部结构
List of 4
$ species : chr [1:4] ...
$ count   : num [1:4] ...
$ observer: chr "Maya"
$ place   : chr "Capybara Creek"
可以看内部结构：
bird_observed 是 List
│
├── species → character vector，长度4
├── count → numeric vector，长度4
├── observer → character，长度1
└── place → character，长度1

## $：从 List 里面拿东西
bird_observed$count -》打开 bird_observed，拿出里面名字叫 count 的东西 -〉2 1 5 13

## $: 也可以往 List 里面加东西
bird_observed$place <- "Capybara Creek" 加了place

## [] & [[]]: [ ] = 保留盒子 [[ ]] = 打开盒子拿内容
```r
x <- list(
    birds = c("toucan", "quetzal"),
    count = c(5, 2)
)
x[["count"]] # 把 count 这个盒子打开，把里面的东西拿出来
x["count"] # 把 count 这个小盒子连着包装一起给我
```

## Data frame = list + equal-length columns
如果7行3列
length(data.frame) = number of columns 因为data frame 底层是 list
```r
length(week_log) # 7
nrow(week_log) # 7
ncol(week_log) # 3
dataframe$column # 这个 data frame 里面的这个 column
is.list(df) # TRUE因为也是list
```

