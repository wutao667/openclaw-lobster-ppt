# 🦞 OpenClaw 养虾入门 PPT - 本地部署指南

> 本文档指导如何从 GitHub 克隆项目并在本地部署演示

---

## 📋 前提条件

- **Git**：已安装并配置
- **Python 3**：用于启动本地 Web 服务器（或使用其他 Web 服务器）
- **GitHub 账号**：用于访问私有仓库（如适用）

---

## 🚀 快速部署（3 步搞定）

### 步骤 1：克隆项目

```bash
# 选择你喜欢的目录
cd ~

# 克隆项目
git clone https://github.com/wutao667/openclaw-lobster-ppt.git

# 进入项目目录
cd openclaw-lobster-ppt
```

### 步骤 2：启动本地服务器

**方法 A：Python 快速服务器（推荐，最简单）**

```bash
# Python 3
python3 -m http.server 8000
```

**方法 B：使用 Node.js http-server**

```bash
# 先安装（如果还没有）
npm install -g http-server

# 启动服务器
http-server -p 8000
```

**方法 C：使用 Nginx/Apache**

将项目文件放到 Web 服务器根目录，或通过配置文件指向项目路径。

### 步骤 3：访问演示

打开浏览器访问：

```
http://localhost:8000
```

或指定文件：

```
http://localhost:8000/openclaw-lobster-presenter.html
```

---

## 📱 手机/平板访问（同一局域网）

如果想在手机上查看：

1. **获取本机 IP 地址**
   ```bash
   # Linux/Mac
   ifconfig | grep "inet "
   
   # Windows
   ipconfig
   ```

2. **手机访问**
   ```
   http://<你的IP地址>:8000
   ```
   例如：`http://192.168.1.100:8000`

---

## 🔄 同步更新

当 GitHub 仓库有更新时：

```bash
cd ~/openclaw-lobster-ppt

# 拉取最新代码
git pull origin main

# 刷新浏览器即可看到更新
```

---

## 🛠️ 常见问题

### Q1: 端口被占用怎么办？

换一个端口：
```bash
python3 -m http.server 8080
# 然后访问 http://localhost:8080
```

### Q2: 如何后台运行服务器？

```bash
# 使用 nohup
nohup python3 -m http.server 8000 &

# 或使用 screen/tmux
screen -S ppt
python3 -m http.server 8000
# Ctrl+A, D 退出 screen（服务器继续运行）
```

### Q3: 如何停止服务器？

```bash
# 找到进程
ps aux | grep "http.server"

# 杀掉进程
kill <PID>
```

### Q4: 图片不显示？

检查文件结构：
```bash
ls -la
# 应该看到：
# - index.html (或 openclaw-lobster-presenter.html)
# - ppt-assets/ (图片文件夹)
```

确保 HTML 文件和 `ppt-assets/` 文件夹在同一目录。

---

## 📂 项目结构

```
openclaw-lobster-ppt/
├── index.html                    # 演示文件（同步自 public_html）
├── ppt-assets/                   # 图片资源文件夹
│   ├── mitsubishi-m320.png
│   ├── iphone-1.jpg
│   ├── case-xxx.png
│   └── ...
├── DEPLOY.md                     # 本部署文档
└── README.md                     # 项目说明
```

---

## 🎯 高级配置

### 使用固定端口（系统服务）

创建 systemd 服务（Linux）：

```bash
sudo nano /etc/systemd/system/ppt-demo.service
```

内容：
```ini
[Unit]
Description=OpenClaw PPT Demo Server
After=network.target

[Service]
Type=simple
User=你的用户名
WorkingDirectory=/home/你的用户名/openclaw-lobster-ppt
ExecStart=/usr/bin/python3 -m http.server 8000
Restart=always

[Install]
WantedBy=multi-user.target
```

启动服务：
```bash
sudo systemctl daemon-reload
sudo systemctl enable ppt-demo
sudo systemctl start ppt-demo
```

---

## 📞 需要帮助？

如有问题，请联系涛哥或检查 GitHub Issues。

**项目地址**: https://github.com/wutao667/openclaw-lobster-ppt

---

_最后更新：2026-03-25_
