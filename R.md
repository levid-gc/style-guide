# R 风格指南

## 标注及命名

### 文件名称

文件名称应以 `.R` 结尾，同时，也要具有意义。

良好：`predict_ad_revenue.R`

不好：<span style="color:red">`foo.R`</span>

### 标识符

标识符中不要使用下划线（`_`）或连字符（`-`）。标识符应按照以下的约定命名。变量名的首选形式为所有的字母都采用小写形式并且单词使用点号分隔（`variable.name`），但是 `variableName` 也是可行的；函数名称的第一个字母采用大写形式并且不需要加点号（`FunctionName`）；常量名称与函数一样，但是最前面需要加上 `k`。

- 首选 `variable.name`，`variableName` 也可行
  - 良好：`avg.clicks`
  - 一般：`avgClicks`
  - 不好：`avg_Clicks`
- `FunctionName`，函数名称要使用动词。但是当创建类对象的时候，函数名称（构造函数）需要与类名匹配（比如，lm）。
  - 良好：`CalculateAvgClicks`
  - 不好：`calculate_avg_clicks`，`calculateAvgClicks`
- `kConstantName`