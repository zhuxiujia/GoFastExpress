# GOFastExpress 一个快速的表达式引擎

### 特性
* 非常简单的抽象语法树
* 尽可能使用强制类型转换代替反射，提高性能
* 参数可以为nil,可以判空，return的变量必须有值或者为nil，不为指针
* 支持语法 `+` `-` `*` `/`  `==` `!=` `>=` `<=`


## 使用方法

#### 判断
```
    var expr="a < 1"
    node, e := Parser(expr)
    v, e := node.Eval(map[string]interface{}{"a": 1})
    if v.(bool) == true{
       //...处理错误e和结果v
    }
```

#### 计算
```
    var expr="a + 1"
    node, e := Parser(expr)
    v, e := node.Eval(map[string]interface{}{"a": 1})
    if v.(int) == 2{
       //...处理错误e和结果v
    }
```