# R 风格指南

[TOC]

## 标注及命名

### 文件名称

文件名称应以 `.R` 结尾，同时，也要具有意义。

良好：`predict_ad_revenue.R`

不好：`foo.R`

### 标识符

标识符中不要使用下划线（`_`）或连字符（`-`）。标识符应按照以下的约定命名。变量名的首选形式为所有的字母都采用小写形式并且单词使用点号分隔（`variable.name`），但是 `variableName` 也是可行的；函数名称的第一个字母采用大写形式并且不需要加点号（`FunctionName`）；常量名称与函数一样，但是最前面需要加上 `k`。

- 首选 `variable.name`，`variableName` 也可行
  - 良好：`avg.clicks`
  - 一般：`avgClicks`
  - 不好：`avg_Clicks`
- `FunctionName`，函数名称要使用动词。_但是当创建类对象的时候除外，函数名称（构造函数）需要与类名匹配（比如，lm）_。
  - 良好：`CalculateAvgClicks`
  - 不好：`calculate_avg_clicks`，`calculateAvgClicks`
- `kConstantName`

## 句法

### 行宽

每行最大的长度为 80 字符。

### 缩进

代码的缩进使用两个空白符。不要使用制表符或混合制表符和空白符。_圆括号中因发生换行而对齐首字符使用到的缩进除外_。

### 空白

所有二元运算符两边留有空白（`=`, `+`, `-`, `<-`, 等等）。_函数调用中当传递参数时使用到的 `=` 两边空白是可选的_。

逗号前不需留有空白，但是逗号后要总是留有空白。

良好：

```R
tab.prior <- table(df[df$days.from.opt < 0, "campaign.id"])
total <- sum(x[, 1])
total <- sum(x[1, ])
```

不好：

```R
tab.prior <- table(df[df$days.from.opt<0, "campaign.id"])  # '<' 两边需要留有空白
tab.prior <- table(df[df$days.from.opt < 0,"campaign.id"])  # 逗号后面需要一个空白
tab.prior<- table(df[df$days.from.opt < 0, "campaign.id"])  # <- 前需要一个空白
tab.prior<-table(df[df$days.from.opt < 0, "campaign.id"])  # <- 两边需要空白
total <- sum(x[,1])  # 逗号后面需要一个空白
total <- sum(x[ ,1])  # 逗号后面需要一个空白，而不是前面
```

除函数调用外，在左圆括号前留有一个空白。

良好：

```R
if (debug)
```

不好：

```R
if(debug)
```

如果能够提升等于或箭头（`<-`）符号的对齐方式，那么多余的空白（比如，一行中多余一个空白）是可以的。

```R
plot(x    = x.coord,
     y    = data.mat[, MakeColName(metric, ptiles[1], "roiOpt")],
     ylim = ylim,
     xlab = "dates",
     ylab = metric,
     main = (paste(metric, " for 3 samples ", sep = "")))
```

圆括号或方括号中代码两边无需留有空白。_逗号后面总留有一个空白除外_。

良好：

```R
if (debug)
x[1, ]
```

不好：

```R
if ( debug )  # debug 两边无需留有空白
x[1,]  # 逗号后面需要留有一个空白
```

### 花括号

左花括号永远不应该单独存在于一行；右花括号应该永远单独存在于一行。当代码块包含一行声明时，您可以忽略花括号；但是您必须始终为单行声明用或是不用花括号保持一致的行为。

```R
if (is.null(ylim)) {
  ylim <- c(0, 0.06)
}
```

或者（两者不能同时存在）

```R
if (is.null(ylim))
  ylim <- c(0, 0.06)
```

为代码块开始总是新建一行。

不好：

```R
if (is.null(ylim)) ylim <- c(0, 0.06)
if (is.null(ylim)) {ylim <- c(0, 0.06)}
```

### else 两边使用花括号

`else` 声明与两边的花括号保持在同一行。

```R
if (condition) {
  one or more lines
} else {
  one or more lines
}
```

不好：

```R
if (condition) {
  one or more lines
}
else {
  one or more lines
}
```

不好：

```R
if (condition)
  one line
else
  one line
```

### 赋值

使用 `<-` 而非 `=`。

良好：`x <- 5`

不好：`x = 5`

### 分号

每一行的结束不需要放置分号，或者使用分号将多个命令放置在同一行。（分号是非必要的，可以将其省略以保持一致性。）

## 代码组织