**[单静][1] 一个简洁的 [同文输入法][2] 主题**

[1]: https://github.com/cxcn/danjing
[2]: https://github.com/osfans/trime

## 预览

<img src="./preview/default.png" width = "400" alt="图片名称" align=center />

更多图片在 `preview` 文件夹下查看

## 按键功能

|  按键  | 手势         | 功能                               |
| :----: | ------------ | :--------------------------------- |
| 第一排 | 下滑         | 输入数字（4 和 7 作为定位）        |
|  空格  | 长按         | 切换中英文                         |
|  退格  | 上滑         | 清屏                               |
|  回车  | 长按         | 进入功能键盘，可以临时切换键盘布局 |
|   o    | 左右滑动     | 输入单个括号                       |
|   g    | 下滑         | 进入编辑键盘                       |
|   n    | 上下左右滑动 | 移动光标                           |

---

## FAQ：

### 1. 怎么设置 26 键（或者其他布局）为默认布局？

在对应的主题文件中搜索 `preset_keyboards`，找到如下字段

```yaml
preset_keyboards:
  __include: danjing:/kbs
```

像下面这样添加一段代码

```yaml
preset_keyboards:
  __include: danjing:/kbs
  <你的方案id>:
    __include: /preset_keyboards/<布局id>
```

| 布局  | id         |
| ----- | ---------- |
| 26 键 | `default`  |
| 27 键 | `qwertys`  |
| 30 键 | `qwerty\_` |

### 2. 怎么修改键盘高度？

为了确保不同布局高度一致，请先修改 _数字_ 和 _符号_ 键盘高度  
使其一致，最后修改 _主键盘_ 高度。

```yaml
# 单静.trime.yaml
# start line: 8

vars:
  # 主键盘
  - &key_height 52 #按键高度
  - &key_height_last 50 # 第4行 按键高度
  - &height_bottom_switch 100 #底部空白开关，0为关，1~100开
  - &height_bottom 6 #底部空白
  - &key_horizontal_gap 3 #按键水平间距
  - &key_vertical_gap 5 #按键行距
  - &off_key_symbol_offset_x 0 #功能键符号偏移
  # 数字、编辑、功能键盘
  - &number_height 60 #按键高度
  - &number_bottom_switch 0 #底部空白开关
  - &number_bottom 1 #底部空白
  # 符号、颜文字键盘
  - &sym_height 50 #按键高度
```

```yaml
# danjing.yaml
# start line: 5

vars:
  # ！不要修改宽度
  #- &sym_height 50 #按键高度 移至 单静.trime.ymal
  - &menu_height 41 #菜单高度
  - &sym_bottom_switch 0 #底部空白开关
  - &sym_bottom 1 #底部空白
```

```yaml
# 单静+.trime.yaml
# start line: 8

vars:
  # 其他在 单静.trime.yaml修改
  # 主键盘
  - &num_height 39 #数字行按键高度
  # 数字、编辑、功能键盘
  - &number_height 71 #按键高度
  # 符号、颜文字键盘
  - &sym_height 61 #按键高度

# `单静+` 的其他高度继承于 `单静`
```
