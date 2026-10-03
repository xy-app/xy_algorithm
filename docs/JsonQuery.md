# JSON 路径查询 (JsonQuery)

基于点分路径与下标语法快速提取多层复杂嵌套 JSON 数据或字典结构中的深层属性内容。

## 权限要求
> 无要求

## 子流程
> 不支持

## 运行参数

* `json` (MixedType)：输入的 JSON 字符串或字典对象。
* `path` (String)：点分检索路径表达式，例如：
  * `data.token`：访问对象深层属性
  * `items[0].id`：访问数组下标及子属性
  * `response.records[1].name`：连续层级检索

## 输出
> 返回查询提取到的节点值，类型自适应映射为数字、字符串、布尔值或元组数组，类型为 `Mixed`。

## 示例
```json
{
  "json": "{\"code\": 200, \"data\": {\"token\": \"xyz123\"}}",
  "path": "data.token"
}
// 输出: "xyz123"
```
