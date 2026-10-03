# 日期时间助手 (DateTimeHelper)

获取当前本地或 UTC 日期时间、生成秒/毫秒级 Unix 时间戳，并支持自定义时间模板格式化与加减秒数偏移计算。

## 权限要求
> 无要求

## 子流程
> 不支持

## 运行参数

* `operation` (String)：时间操作指令，支持：
  * `now` / `current`：获取格式化后的当前本地时间
  * `utc_now`：获取格式化后的当前 UTC 时间
  * `timestamp`：获取当前 Unix 时间戳（秒级）
  * `timestamp_ms`：获取当前 Unix 时间戳（毫秒级）
* `format_str` (String)：时间格式化模板字符串（基于标准 strftime 规则，如 `%Y-%m-%d %H:%M:%S` 或 `%Y年%m月%d日`）。
* `offset_seconds` (MixedType)：时间偏移秒数，正数表示未来，负数表示过去（例如 `3600` 表示向后推移 1 小时，`-86400` 表示前一天）。

## 输出
* 针对 `now` / `utc_now`：返回格式化后的日期时间字符串 `string`。
* 针对 `timestamp` / `timestamp_ms`：返回整型时间戳数值 `number`。

## 示例
```json
{
  "operation": "now",
  "format_str": "%Y-%m-%d %H:%M:%S",
  "offset_seconds": 86400
}
// 输出明天的此时时间字符串
```
