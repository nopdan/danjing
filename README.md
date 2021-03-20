
**一个简洁的 [同文输入法](https://github.com/osfans/trime) 主题**

## 按键功能

| 按键 | 手势         | 功能                               |
| :--: | ------------ | :--------------------------------- |
| 空格 | 长按         | 切换中英文                         |
| 退格 | 上滑         | 清屏                               |
| 回车 | 长按         | 进入功能键盘，可以临时切换键盘布局 |
|  o   | 左右滑动     | 输入单个括号                       |
|  g   | 下滑         | 进入编辑键盘                       |
|  n   | 上下左右滑动 | 移动光标                           |

---

## FAQ：

### 1. 怎么设置 26 键（或者其他布局）为默认布局？

在对应的主题文件中搜索 preset_keyboards，找到如下字段

```yaml
preset_keyboards:
  __include: xingaqr:/kbs
```

像下面这样添加一段代码

```yaml
preset_keyboards:
  __include: xingaqr:/kbs
  <你的方案id>:
    __include: /preset_keyboards/<布局id>
```

> | 布局  | id       |
> | ----- | -------- |
> | 26 键 | default  |
> | 27 键 | qwertys  |
> | 30 键 | qwerty\_ |

### 2. 怎么修改键盘高度？

*底部空白的高度优先修改，默认只开启主键盘的底部空白*

#### 2.1 怎么修改 `单静` 键盘高度？

> 为了确保不同布局高度一致，请按照修改顺序进行修改

键盘高度的定义在 `单静.trime.yaml` 里的第 8 行  
符号键盘菜单高度定义在 `xingaqr.yaml` 里的第 9 行  
修改顺序：

- `number_height` #数字键盘按键高度
- `sym_height` #符号键盘按键高度
- `menu_height` #符号键盘菜单高度 #微调
- `key_height` #按键高度
- `key_height_last` # 第 4 行 按键高度 #微调

#### 2.2 怎么修改 `单静h` 键盘高度？

> 主键盘的参数都在 `单静.trime.yaml` 里设置，下面的在 `单静h` 里设置

修改顺序：
- 修改 `number_height` 和 `sym_height` 高度
- 使数字键盘和符号键盘高度一致
- 修改 `num_height` 进行微调
