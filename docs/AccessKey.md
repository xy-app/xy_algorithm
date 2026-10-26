# 读取字典键值 (AccessKey)

根据指定的 Key 名称查询字典、Map 或 JSON 字符串中的对应内容。

## 权限要求
> 无要求

## 运行参数

* `map` (MixedType)：目标字典或 JSON 对象，支持字典对象、Map、变量引用或 JSON 格式字符串。
* `key` (MixedType)：要读取的目标键名（Key）。

## 输出
> 返回字典中与指定键对应的值对象，类型为 `Mixed`。如果键不存在，返回空值。

## 示例
```json
{
  "map": "{\"name\": \"Alice\", \"age\": 30}",
  "key": "name"
}
// 输出: "Alice"
```
