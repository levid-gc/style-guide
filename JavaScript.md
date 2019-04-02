
# JavaScript 风格指南

## 命名

### 标识符通用规则

标识符中仅包含 ASCII 字母及数字，并且，很少情况下会使用到下划线和美元符号（极少，仅在框架需要的时候，比如，Angular）。

在合理的范围内，尽量使用具有描述性的名称。不对项目之外的读者使用含糊不清或不熟悉的缩写，并且缩写不能采用删除一个单词内的字母的方式。

```javascript
priceCountReader      // 无缩写
numErrors             // "num" 是一个惯用约定。
numDnsConnections     // 多数人明白 "DNS" 的含义。
```

不合法：

```javascript
n                     // 无意义。
nErr                  // 含糊缩写。
nCompConns            // 含糊缩写。
wgcConnections        // 仅仅您的小组明白这是什么意思。
pcReader              // 许多事物都可以缩写为 "pc"。
cstmrId               // 删除了中间字符。
kSecondsPerDay        // 勿使用匈牙利式的标记。
```

### 各类型标识符规则

#### 包名

包名一律采用 `lowerCamelCase` 形式。比如，`my.exampleCode.deepSpace`，而不是 `my.examplecode.deepspace` 或者 `my.example_code.deep_space`。
