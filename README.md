# 🦞 OpenClaw 养虾入门

> 基于 reveal.js 的极简科技感演示文稿 · OpenClaw 智能助手入门指南

[![GitHub](https://img.shields.io/badge/github-repo-blue?logo=github)](https://github.com/wutao667/openclaw-lobster-ppt)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

---

## 📖 项目简介

这是一个为 **OpenClaw 智能助手** 打造的演示文稿项目，主题为《养虾入门》。采用极简科技风设计，支持：

- ✨ **竖屏演示** - 适配手机/平板移动端
- 🎨 **暗黑极客风** - 高对比度配色，代码高亮
- 🖼️ **智能配图** - 每页精选科技感插图
- 📝 **演讲稿备注** - 每页附带详细演讲备注
- 🔄 **自动同步** - 支持 GitHub 自动部署

---

## 🎯 在线演示

**👉 立即观看**: https://wutao667.github.io/openclaw-lobster-ppt/

---

## 📋 目录结构

```
openclaw-lobster-ppt/
├── index.html                    # 演示主文件（33 页幻灯片）
├── ppt-assets/                   # 图片资源文件夹
│   ├── mitsubishi-m320.png
│   ├── iphone-1.jpg
│   ├── case-xxx.png
│   └── ...
├── README.md                     # 项目说明（本文件）
└── DEPLOY.md                     # 详细部署指南
```

---

## 🚀 快速开始

### 方式 1：在线访问（推荐）

直接打开：https://wutao667.github.io/openclaw-lobster-ppt/

### 方式 2：本地部署

```bash
# 1. 克隆项目
git clone https://github.com/wutao667/openclaw-lobster-ppt.git
cd openclaw-lobster-ppt

# 2. 启动本地服务器
python3 -m http.server 8000

# 3. 浏览器访问
# http://localhost:8000
```

**详细部署指南请查看**: [DEPLOY.md](DEPLOY.md)

---

## 🎨 功能特性

| 特性 | 说明 |
|------|------|
| **响应式设计** | 自动适配桌面/手机/平板 |
| **暗黑主题** | 极客风深色背景，保护视力 |
| **代码高亮** | 支持多种编程语言语法高亮 |
| **演讲稿备注** | 每页附带演讲者备注（按 `S` 键查看） |
| **键盘导航** | 方向键/空格键翻页 |
| **触摸支持** | 支持手机滑动手势 |

---

## ⌨️ 快捷键

| 按键 | 功能 |
|------|------|
| `→` / `↓` / `空格` | 下一页 |
| `←` / `↑` | 上一页 |
| `S` | 显示/隐藏演讲稿备注 |
| `F` | 全屏模式 |
| `ESC` | 退出全屏 |

---

## 📱 手机访问

在同一局域网下：

1. 获取本机 IP：`ifconfig | grep "inet "`
2. 手机访问：`http://<你的 IP>:8000`

---

## 🔄 更新同步

```bash
cd openclaw-lobster-ppt
git pull origin main
# 刷新浏览器即可
```

---

## 🛠️ 开发说明

### 编辑幻灯片

直接编辑 `index.html` 文件，每个 `<section>` 标签代表一页幻灯片。

```html
<!-- 第 X 页：标题 -->
<section>
  <h2>页面标题</h2>
  <ul>
    <li>内容 1</li>
    <li>内容 2</li>
  </ul>
  <aside class="notes">
    这里是演讲稿备注...
  </aside>
</section>
```

### 添加图片

将图片放入 `ppt-assets/` 文件夹，然后在 HTML 中引用：

```html
<img src="ppt-assets/your-image.png" alt="描述">
```

---

## 📄 许可证

MIT License

---

## 👤 作者

**涛哥** · OpenClaw 智能助手

---

_最后更新：2026-03-26_
