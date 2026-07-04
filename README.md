# 🧈 小黄油 Little Butter Icons — Zed 图标主题扩展

糖果色文件图标主题，按家族色编码。需配合 **[little-butter](https://github.com/ikun-Lg/LG-Theme-for-zed)** 配色扩展一起使用。

本仓库是 [VS Code 版 lggbond-theme](https://github.com/ikun-Lg/LG-Theme-for-vscode) 图标集的 Zed 移植。

## ✨ 内容

- **139 种文件扩展名**映射（js/ts/py/go/rs/java/c/...）
- **61 个特殊文件名**精确匹配（README.md / Dockerfile / Makefile / .gitignore / vite.config.ts / ...）
- **70 个 SVG 图标**，按糖果家族色分组：

| 家族 | 颜色 | 覆盖 |
| --- | --- | --- |
| 🧈 web 系列 | 暖金色 | html / vue / svelte / astro / jsx / tsx / css / scss / graphql |
| 🍓 doc 系列 | 粉棕色 | md / txt / pdf / doc |
| 🟣 style 系列 | 紫色 | sass / less / 配置文件 |
| 🟢 systems 系列 | 绿色 | python / go / rust / c / swift |
| 🔵 data 系列 | 蓝色 | json / xml / sql / csv / yaml / toml |

## 🚀 安装

本扩展是图标主题，**必须配合 `little-butter` 配色扩展**一起使用。两个都要装：

```bash
# 在 Zed 中打开命令面板 (cmd+shift+p)
# 分别对两个目录执行 "zed: install dev extension"
zed /Users/luoguang/Documents/git/lg-theme-zed       # 配色
zed /Users/luoguang/Documents/git/lg-theme-zed-icons  # 图标
```

安装后，在 settings.json 中启用：

```jsonc
{
  "theme": "Little Butter",                    // 或 "Little Butter Flat"
  "file_icons": "小黄油 Little Butter Icons"
}
```

## 📁 结构

```
lg-theme-zed-icons/
├── extension.toml      # 扩展清单 (id=little-butter-icons)
├── icon_theme.json     # Zed 图标主题清单 (schema v0.3.0)
├── icons/              # 70 个 SVG 图标
├── README.md
└── LICENSE             # MIT
```

## 🛠️ 开发

修改图标后保存，Zed 会自动热重载图标主题。校验：

```bash
# 校验 JSON 格式
python3 -m json.tool icon_theme.json

# 校验所有 SVG 路径引用（需 pip install jsonschema）
python3 - <<'EOF'
import json, os
from jsonschema import Draft7Validator
ROOT = '/Users/luoguang/Documents/git/lg-theme-zed-icons'
schema = json.load(open('/tmp/zed-icon-schema.json'))
t = json.load(open(f'{ROOT}/icon_theme.json'))
errs = list(Draft7Validator(schema).iter_errors(t))
print(f'schema errors: {len(errs)}')
fx = t['themes'][0]['file_icons']
bad = [(n, i['path']) for n, i in fx.items() if not os.path.exists(f'{ROOT}/{i["path"]}')
print(f'missing SVG files: {len(bad)}')
EOF
```

## 📝 清单 (extension.toml)

| 属性 | 值 |
| --- | --- |
| id | `little-butter-icons` |
| version | `1.0.0` |
| icon_themes | `["icon_theme.json"]` |

## 📄 协议

MIT © lggbond
