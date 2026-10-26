# 日期时间助手 (DateTimeHelper)

获取当前本地或 UTC 日期时间、生成秒/毫秒/微秒级 Unix 时间戳，并支持 ISO-8601 / RFC 3339 格式化与加减秒数偏移计算。

## 权限要求
> 无要求

## 运行参数

* `operation` (String)：时间操作指令，支持：
  * `now` / `current`：获取格式化后的当前本地时间
  * `utc_now`：获取格式化后的当前 UTC 时间
  * `timestamp`：获取当前 Unix 时间戳（秒级）
  * `timestamp_ms`：获取当前 Unix 时间戳（毫秒级）
  * `timestamp_us`：获取当前 Unix 时间戳（微秒级）
  * `iso8601` / `rfc3339`：获取 ISO-8601 标准格式化时间字符串（如 `2025-02-23T12:34:56.789Z`）
* `format_str` (String)：时间格式化模板字符串（基于标准 strftime 规则，如 `%Y-%m-%d %H:%M:%S` 或 `%Y年%m月%d日`）。
* `offset_seconds` (MixedType)：时间偏移秒数，正数表示未来，负数表示过去（例如 `3600` 表示向后推移 1 小时，`-86400` 表示前一天）。

## 输出
* 针对 `now` / `utc_now` / `iso8601`：返回格式化后的日期时间字符串 `string`。
* 针对 `timestamp` / `timestamp_ms` / `timestamp_us`：返回整型时间戳数值 `number`。

## 示例
```json
{
  "operation": "now",
  "format_str": "%Y-%m-%d %H:%M:%S",
  "offset_seconds": 86400
}
// 输出明天的此时时间字符串
```
