# 矩形几何计算 (RectOperations)

对矩形区域 `(x, y, w, h)` 或多边形执行几何运算，包括中心点计算、点在矩形内判定、射线法点在多边形内判定、多矩形外接包围盒合并、矩形平移与外扩/内缩。

## 权限要求
> 无要求

## 运行参数

* `rect` (MixedType)：输入的矩形四元组数据 `(x, y, w, h)`，或多边形点集 `x1,y1, x2,y2, ...`，或多矩形集合 `"10,10,20,20; 50,50,30,30"`。
* `operation` (String)：几何计算模式，支持：
  * `center`：计算矩形几何中心点坐标
  * `contains_point` / `contains`：判定指定坐标点是否位于矩形内部
  * `contains_polygon` / `contains_poly`：基于射线法（Ray-Casting）判定点是否在多边形内部
  * `union_bbox` / `bbox`：计算多个矩形的最小外接包围盒 (Bounding Box)
  * `offset`：沿 X/Y 轴平移矩形
  * `expand`：以矩形中心为基准按宽高外扩或内缩矩形
  * `bottom_right`：获取矩形右下角端点坐标
* `param` (MixedType)：几何计算辅助参数：
  * 在 `contains` / `contains_polygon` 模式下：为待判定目标点坐标 `"px, py"`
  * 在 `offset` 模式下：为平移偏移量 `"dx, dy"`
  * 在 `expand` 模式下：为宽高增量 `"dw, dh"`（负数表示向内缩进）

## 输出
* 针对 `center` / `bottom_right`：返回点坐标元组 `(x, y)`，类型为 `Tuple`。
* 针对 `contains` / `contains_polygon`：包含返回 `1`，不包含返回 `0`，类型为 `number`。
* 针对 `offset` / `expand` / `union_bbox`：返回变换或计算后的新矩形四元组 `(x, y, w, h)`，类型为 `Tuple`。

## 示例
```json
{
  "rect": "0,0, 100,0, 100,100, 0,100",
  "operation": "contains_polygon",
  "param": "50, 50"
}
// 输出: 1
```
