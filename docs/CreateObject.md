# 创建对象 (CreateObject)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
在内存中创建结构化数据实体，支持多种常用基础几何与数值实体模板（Point、Rect、Size、Color、Range、DateTime、Dict、Tuple 等）。

## 运行参数

* **数据载荷/模板 (`value`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 字面量、JSON 模板或构造表达式。支持创建坐标点、矩形区域、颜色值、数值区间、日期时间、数组字典等。
  * 常见预设：
    * `{"x": 0, "y": 0}` (坐标点)
    * `{"width": 1920, "height": 1080}` (尺寸大小)
    * `{"x": 0, "y": 0, "width": 1920, "height": 1080}` (矩形区域)
    * `{"r": 255, "g": 0, "b": 0, "a": 255}` (颜色值)
    * `0..100` (数值区间)
    * `now` (当前时间)
    * `[1, 2, 3]` (列表数组)

## 输出

* 类型: `Mixed`
* 描述: 成功构造生成的结构化数据对象。

## 使用示例

```json
{
  "tag": "CreateObject",
  "value": "{\"x\": 100, \"y\": 200}"
}
```
