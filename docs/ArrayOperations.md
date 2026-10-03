# 集合综合运算 (ArrayOperations)

对数组或元组执行一站式全能集合算法操作，包括排序、反转、去重、包含判定、元素查找、切片提取、元素追加与末尾弹出。

## 权限要求
> 无要求

## 子流程
> 不支持

## 运行参数

* `array` (MixedType)：输入的目标元组数组、对象列表或 JSON 数组。
* `operation` (String)：操作指令，支持以下模式：
  * `sort`：正序排列数组元素
  * `reverse`：反转数组元素次序
  * `unique`：去除数组中的重复项并保留首次出现顺序
  * `contains`：判断数组是否包含参数指定的元素值（包含返回 1，不包含返回 0）
  * `index_of`：查找指定元素在数组中的索引位置（从 0 开始，未找到返回 -1）
  * `slice`：提取数组切片子集（参数格式为 `"start, end"` 或 `"start"`）
  * `push` / `push_back`：向现有数组尾部追加新元素，返回更新后的新数组
  * `pop` / `pop_back`：从数组末尾弹出并返回最后一个元素
  * `remove_at`：移除指定索引位置的元素，返回更新后的新数组
* `param` (MixedType)：操作附加参数：
  * 在 `push` 模式下：为待追加的新元素值
  * 在 `contains` / `index_of` 模式下：为待匹配的目标元素值
  * 在 `slice` 模式下：为区间范围字符串（如 `"0, 2"`）
  * 在 `remove_at` 模式下：为待移除元素的索引下标（如 `1`）

## 输出
* 针对 `push` / `sort` / `reverse` / `unique` / `slice` / `remove_at`：返回变换后的全新元组数组 `Tuple`。
* 针对 `pop`：返回弹出的末尾元素对象。
* 针对 `contains` / `index_of`：返回整型数值 `Number`。

## 示例
```json
// 去重
{
  "array": ["apple", "banana", "apple", "orange"],
  "operation": "unique",
  "param": ""
}
// 输出: ["apple", "banana", "orange"]
```
