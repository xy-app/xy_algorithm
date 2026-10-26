# 正则表达式处理 (RegexProcess)

使用正则表达式执行模式匹配判定、首项提取、全部项捕获或内容替换。

## 权限要求
> 无要求

## 运行参数

* `text` (MixedType)：待处理的目标原始输入文本。
* `pattern` (MixedType)：符合标准 PCRE 规范的正则表达式模式字符串（如 `\d+`, `https?://\S+`）。
* `action_type` (String)：正则表达式处理动作模式，支持：
  * `match` / `is_match`：检查是否匹配正则规则，返回布尔值 `1` 或 `0`
  * `extract`：提取匹配到的捕获组或首个匹配项
  * `extract_all`：全量提取所有匹配项，返回字符串元组数组
  * `replace`：将所有匹配到的内容替换为指定的新文本
* `replacement` (MixedType)：替换文本（仅在 `action_type = replace` 时生效）。

## 输出
* 针对 `match`：返回布尔值数值（`1` 为匹配，`0` 为不匹配）。
* 针对 `extract` / `replace`：返回提取或替换后的文本字符串 `string`。
* 针对 `extract_all`：返回所有匹配项元组数组 `Tuple`。

## 示例
```json
{
  "text": "Order ID: #12345 confirmed",
  "pattern": "#(\\d+)",
  "action_type": "extract",
  "replacement": ""
}
// 输出: "12345"
```
