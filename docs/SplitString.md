# 拆分字符串 (SplitString)

按照指定分隔符将整段文本分割拆解为多个子字符串组成的元组列表。

## 权限要求
> 无要求

## 子流程
> 不支持

## 运行参数

* `text` (MixedType)：待拆分的原始文本字符串。
* `delimiter` (MixedType)：拆分分隔符，支持单字符或多字符（如 `,`, `-`, `\n`, ` `）。若分隔符为空，则按字符逐个拆分。

## 输出
> 返回拆分后的字符串列表，类型为 `Tuple`。

## 示例
```json
{
  "text": "apple,banana,orange",
  "delimiter": ","
}
// 输出: ("apple", "banana", "orange")
```
