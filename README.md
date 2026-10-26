# 🧮 官方核心数据算法与文本变换套件 (Data Algorithm & Text Transform Suite)

[![Plugin Version](https://img.shields.io/badge/version-0.53.0-blue.svg)](manifest.json)
[![Group](https://img.shields.io/badge/group-Algorithm-orange.svg)](#)
[![Platform](https://img.shields.io/badge/platform-All-green.svg)](#)
[![License](https://img.shields.io/badge/license-Freeware-brightgreen.svg)](#)
[![Discord](https://img.shields.io/discord/832082456727257118?label=Discord&logo=discord&logoColor=white&color=5865F2)](https://discord.gg/g5Fh3FtfGx)

企业级数据结构处理、文本清洗转换、自动化坐标生成与实用数学算法套件。专为自动化脚本、RPA 流程、后端任务编排以及数据流清洗设计。

---

## 📖 简介 (Overview)

`xy_algorithm` 提供了全套高效、鲁棒的数据操作指令，涵盖企业级数组与字典存取与运算、JSONPath 多层级路径提取、文本切分拼接、正则表达式高级匹配与替换、Base64/URL 编码转换、随机数与坐标扰动仿真、几何网格矩阵生成、日期时间与时间戳处理以及 MD5/SHA256 哈希摘要计算。

---

## ✨ 核心特性 (Features)

- **集合与字典操作**：支持数组正负下标读写、切片、去重、排序、入栈出栈及键值高效检索。
- **JSONPath 多层解析**：支持形如 `data.items[0].id` 的嵌套路径查询。
- **文本与正则引擎**：包含高性能字符串切分、拼接、Unicode 安全截取、正则匹配与替换、Base64 / URL 编解码。
- **拟人化防封坐标系统**：提供圆盘随机抖动扰动（Humanize Jitter）与批量行×列网格生成，助力游戏自动化与 UI 遍历点击。
- **几何与数学统计**：支持矩形判定、平移与缩放，以及求和、均值、极值与四则/幂次运算。
- **时序与加密安全**：高精度时间戳与格式化，支持 MD5 与 SHA-256 散列加密。

---

## 🛠️ 动作指令全景速查 (Action Catalog)

| 动作标识 (Tag) | 功能名称 | 描述 | 输出类型 |
| :--- | :--- | :--- | :--- |
| `AccessArray` | 访问数组元素 | 按索引下标读取/修改/弹出元素项，支持负数索引 | `Mixed` |
| `AccessKey` | 读取字典键值 | 查询 JSON 字符串、字典或 Map 中的指定键 | `Mixed` |
| `ArraySize` | 获取数组长度 | 计算元组、列表、JSON 数组或文本的元素长度 | `number` |
| `ArrayOperations`| 集合综合运算 | 排序、反转、去重、包含判定、查找、切片、push/pop | `Mixed` |
| `JsonQuery` | JSON 路径查询 | 使用点分路径与下标递归提取多层深层属性 | `Mixed` |
| `SubString` | 截取子字符串 | 按下标与长度截取文本，支持负数索引与 Emoji | `string` |
| `SplitString` | 拆分字符串 | 按分隔符将字符串拆分为元组数组 | `Tuple` |
| `JoinString` | 连接字符串列表 | 使用指定分隔符将元组或列表拼接为文本 | `string` |
| `RegexProcess` | 正则表达式处理 | 模式判定、单项捕获、全量提取 (`extract_all`) 与正则替换 | `Mixed` |
| `TextTransform` | 文本格式转换 | Trim、大小写转换、Base64 编解码与 URL 编解码 | `string` |
| `RandomNumber` | 生成随机数字 | 在指定区间 (`0..100`, `0.0..1.0`) 生成随机整数/浮点数 | `number` |
| `MathEval` | 数值统计与运算 | 数组求和、平均值、极值、舍入四舍五入与算术运算 | `real` |
| `DateTimeHelper`| 日期时间助手 | 获取当前时间、秒/毫秒时间戳与加减秒偏移计算 | `Mixed` |
| `RandomPoint` | 生成随机坐标点 | 基于中心点与扰动半径进行圆盘抖动，模拟真人点击 | `Tuple` |
| `RectOperations`| 矩形几何计算 | 几何中心点计算、点在矩形内判定、平移与尺寸膨胀 | `Mixed` |
| `GridGenerator` | 网格矩阵生成 | 批量生成行×列网格矩阵坐标，适用于背包/列表项遍历 | `Tuple` |
| `HashDigest` | 哈希摘要计算 | 计算明文文本的 MD5 或 SHA-256 散列值 | `string` |

---

## 📚 详细参数说明与使用示例 (Detailed Reference)

### 1. 数据结构与 JSON 查询

#### `AccessArray` - 访问数组元素
- **参数：**
  - `value` (*string*, 默认 `()`): 数组/元组对象引用。
  - `index` (*number*, 默认 `0`): 目标下标（支持 `-1` 读取末项）。
- **输出：** `Mixed`

#### `AccessKey` - 读取字典键值
- **参数：**
  - `map` (*string*, 默认 `{}`): 字典或 JSON 文本。
  - `key` (*string*, 必填): 目标键名。
- **输出：** `Mixed`

#### `ArrayOperations` - 集合综合运算
- **参数：**
  - `array` (*tuple*, 默认 `()`): 输入数组。
  - `operation` (*string*, 可选: `sort`, `reverse`, `unique`, `filter_empty`, `flatten`, `contains`, `index_of`, `slice`, `push`, `pop`, `remove_at`)。
  - `param` (*string*): 操作附加参数（如切片范围 `0,2` 或待查找的值）。
- **输出：** `Mixed`

#### `JsonQuery` - JSON 路径查询
- **参数：**
  - `json` (*string*, 默认 `{}`): JSON 文本或字典对象。
  - `path` (*string*): 点分路径与切片，如 `data.items[0].id`、`data.items[*].name`（通配全量提取）、`items[0:5]`（范围切片）。
- **输出：** `Mixed`

---

### 2. 文本清洗与正则表达式

#### `SubString` - 截取子字符串
- **参数：**
  - `text` (*string*): 原始文本。
  - `start` (*number*, 默认 `0`): 起始字符下标。
  - `length` (*number*, 默认 `-1`): 截取长度（-1 表示截取至末尾）。
- **输出：** `string`

#### `SplitString` - 拆分字符串
- **参数：**
  - `text` (*string*): 原始文本。
  - `delimiter` (*string*, 默认 `,`): 分隔符。
- **输出：** `Tuple`

#### `JoinString` - 连接字符串列表
- **参数：**
  - `array` (*tuple*, 默认 `()`): 输入元组或数组。
  - `delimiter` (*string*, 默认 `,`): 连接分隔符。
- **输出：** `string`

#### `RegexProcess` - 正则表达式处理
- **参数：**
  - `text` (*string*): 原始输入文本。
  - `pattern` (*string*, 默认 `\d+`): 正则表达式。
  - `action_type` (*string*, 可选: `match`, `extract`, `extract_all`, `replace`): 操作类型。
  - `replacement` (*string*): 替换文本（仅在 `action_type = replace` 时生效）。
- **输出：** `Mixed`（提取返回匹配项或列表，匹配返回布尔值，替换返回新文本）。

#### `TextTransform` - 文本格式转换
- **参数：**
  - `text` (*string*): 输入文本。
  - `operation` (*string*, 默认 `trim`):
    - `trim`: 去除首尾空白
    - `to_lower` / `to_upper`: 大小写转换
    - `base64_encode` / `base64_decode`: Base64 编解码
    - `url_encode` / `url_decode`: URL 百分号编解码
- **输出：** `string`

---

### 3. 几何、自动化与拟人化仿真

#### `RandomPoint` - 拟人化随机坐标点
- **参数：**
  - `center` (*string*, 默认 `100, 100`): 基准坐标点。
  - `radius` (*number*, 默认 `10`): 扰动抖动半径（像素）。
- **输出：** `Tuple` (形如 `(X, Y)`)

#### `GridGenerator` - 网格矩阵生成
- **参数：**
  - `start_point` (*string*, 默认 `100, 100`): 左上角起始原点坐标。
  - `rows` (*number*, 默认 `3`): 网格行数。
  - `cols` (*number*, 默认 `3`): 网格列数。
  - `step` (*string*, 默认 `50, 50`): 水平与垂直间距步长 `(DX, DY)`。
- **输出：** `Tuple` (所有网格点的坐标列表)

#### `RectOperations` - 矩形几何计算
- **参数：**
  - `rect` (*string*, 默认 `0, 0, 100, 100`): 矩形四元组 `(X, Y, W, H)`、多边形点集或多矩形集合。
  - `operation` (*string*, 可选: `center`, `contains_point`, `contains_polygon`, `union_bbox`, `offset`, `expand`, `bottom_right`)。
  - `param` (*string*): 点坐标 `PX, PY` 或偏移缩放量 `DX, DY`。
- **输出：** `Mixed`

---

### 4. 数学统计与加密助手

#### `MathEval` - 数值统计与运算
- **支持操作：** `sum`, `avg`, `min`, `max`, `round`, `abs`, `add`, `sub`, `mul`, `div`, `pow`
- **参数：**
  - `operation` (*string*): 运算指令。
  - `values` (*string*): 逗号分隔的数字序列或元组。
  - `param` (*number*): 附加参数（如舍入位数或第二操作数）。
- **输出：** `real`

#### `HashDigest` - 哈希摘要计算
- **参数：**
  - `text` (*string*): 原始输入文本。
  - `algorithm` (*string*, 可选 `sha256` / `md5`): 加密算法。
- **输出：** `string` (十六进制摘要字符串)

---

## 📦 插件配置结构 (Manifest Reference)

```json
{
  "plugin_id": "xy_algorithm",
  "name": "数据算法与文本工具 (Data & Text Tools)",
  "version": "0.50.5",
  "group": "Algorithm",
  "group_icon": "🧮",
  "actions": [...]
}
```

---

## 📄 许可证 (License)

本插件遵循免费专有许可协议 (Freeware)。供 小友+ 用户免费下载与使用，未经官方书面授权，严禁对二进制文件进行逆向工程、反编译或二次打包转售。
