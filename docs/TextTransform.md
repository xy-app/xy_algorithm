# 文本格式转换 (TextTransform)

提供现代自动化流程中核心的文本清洗与编码转换工具，包括去除首尾空白、大小写切换、Base64 编解码与 URL 编解码。

## 权限要求
> 无要求

## 子流程
> 不支持

## 运行参数

* `text` (MixedType)：待变换的目标文本字符串。
* `operation` (String)：转换操作类型，支持：
  * `trim`：去除字符串首尾空白字符
  * `to_lower`：转换为全小写英文
  * `to_upper`：转换为全大写英文
  * `base64_encode`：进行 Base64 编码
  * `base64_decode`：进行 Base64 解码并还原为 UTF-8 文本
  * `url_encode`：进行 URL 百分号转义编码
  * `url_decode`：进行 URL 百分号还原解码

## 输出
> 返回转换后的全新文本字符串，类型为 `string`。

## 示例
```json
{
  "text": "Hello World",
  "operation": "base64_encode"
}
// 输出: "SGVsbG8gV29ybGQ="
```
