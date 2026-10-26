# JSON 路径查询 (JsonQuery)

基于点分路径与下标语法快速提取多层复杂嵌套 JSON 数据或字典结构中的深层属性内容，支持通配符全量提取与范围切片。

## 权限要求
> 无要求

## 运行参数

* `json` (MixedType)：输入的 JSON 字符串或字典对象。
* `path` (String)：点分检索路径表达式，例如：
  * `data.token`：访问对象深层属性
  * `items[0].id`：访问数组下标及子属性
  * `items[*].name`：通配符提取数组中所有对象的 `name` 字段
  * `items[0:5]`：提取数组前 5 项元素（范围切片切分）
  * `response.records[1].name`：连续层级检索

## 输出
> 返回查询提取到的节点值，类型自适应映射为数字、字符串、布尔值或元组数组，类型为 `Mixed`。

## 示例
```json
{
  "json": "{\"items\": [{\"name\": \"Alice\"}, {\"name\": \"Bob\"}]}",
  "path": "items[*].name"
}
// 输出: ("Alice", "Bob")
```
