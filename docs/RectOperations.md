# 矩形几何计算 (RectOperations)

对矩形区域 `(x, y, w, h)` 执行几何运算，包括中心点计算、点在矩形内判定、矩形平移与外扩/内缩。

## 权限要求
> 无要求

## 子流程
> 不支持

## 运行参数

* `rect` (MixedType)：输入的矩形四元组数据，格式支持元组 `(x, y, w, h)` 或逗号分隔字符串 `"x, y, w, h"`。
* `operation` (String)：几何计算模式，支持：
  * `center`：计算矩形几何中心点坐标
  * `contains_point` / `contains`：判定指定坐标点是否位于矩形内部
  * `offset`：沿 X/Y 轴平移矩形
  * `expand`：以矩形中心为基准按宽高外扩或内缩矩形
  * `bottom_right`：获取矩形右下角端点坐标
* `param` (MixedType)：几何计算辅助参数：
  * 在 `contains` 模式下：为待判定目标点坐标 `"px, py"`
  * 在 `offset` 模式下：为平移偏移量 `"dx, dy"`
  * 在 `expand` 模式下：为宽高增量 `"dw, dh"`（负数表示向内缩进）

## 输出
* 针对 `center` / `bottom_right`：返回点坐标元组 `(x, y)`，类型为 `Tuple`。
* 针对 `contains`：包含返回 `1`，不包含返回 `0`，类型为 `number`。
* 针对 `offset` / `expand`：返回变换后的新矩形四元组 `(x, y, w, h)`，类型为 `Tuple`。

## 示例
```json
{
  "rect": "100, 200, 400, 300",
  "operation": "center",
  "param": ""
}
// 输出: (300, 350)
```
