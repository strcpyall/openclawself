<h1 align="center">OpenClaw 独立版</h1>

<p align="center">
  <b>零依赖、下载即用、数据隔离、支持多实例</b>
</p>

<p align="center">
  <a href="https://www.openclawself.com">🌐 官方网站</a>
  ·
  <a href="#-加入社区">💬 交流群</a>
  ·
  <a href="#-商务合作">🤝 合作咨询</a>
</p>

<p align="center">
  <a href="https://www.openclawself.com/download">
    <img src="https://img.shields.io/badge/⬇️%20前往官网下载-立即获取-blue?style=for-the-badge" alt="前往官网下载"/>
  </a>
</p>

---

## ✨ 核心特性

| 特性 | 说明 |
|------|------|
| 🎒 **便携免安装** | 解压即用，无需配置环境 |
| 🏢 **多实例支持** | 单设备可运行多个独立实例 |
| 💾 **数据隔离** | 配置与数据完全独立存储** |
| 🚀 **一键启动** | 双击或一条命令快速运行 |
| 🔒 **硬件绑定** | 安全授权，防止非法复制 |

---

## 🌐 官方网站

**https://www.openclawself.com**

<p align="center">
  <a href="https://www.openclawself.com/download" style="display:inline-block;padding:12px 24px;background:#2563eb;color:#fff;border-radius:6px;text-decoration:none;font-weight:bold;">
    ⬇️ 前往官网下载最新版本
  </a>
</p>

访问官网获取：📖 文档教程 · 🎬 视频演示 · 💾 版本下载 · 🆘 常见问题

---

## 💬 加入社区

<p align="center">
  <img src="docs/images/qrcode.png" alt="OpenClaw 交流群" width="180"/>
  <br/>
  <sub>微信扫码加入群聊</sub>
</p>

**群功能**：技术支持 · 功能讨论 · 使用心得 · 版本更新通知

---

## 🤝 商务合作

| 合作方向 | 描述 |
|---------|------|
| 🤖 AI 模型厂商 | 集成更多大模型 |
| 🏢 企业服务商 | 私有化部署与定制 |
| 📝 技术作者 | 教程与案例分享 |
| 💡 产品体验官 | 内测与反馈 |

**联系方式**：📧 626992497@qq.com · 💬微信 ai_team_lab（备注：AI合作）

---

## 🚀 快速开始

### 1. 解压
将压缩包解压到目标设备

### 2. 首次安装

**macOS**
```bash
双击 Start.command
# 或
./openclaw install
```

**Linux**
```bash
cd /path/to/openclaw
./install.sh
# 或
./openclaw install
```

**Windows**
```powershell
双击 Start.vbs
# 或
.\openclaw.exe install
```

### 3. 访问
```
http://localhost:8765
```

---

## 🖥️ 常用命令

| 命令 | 说明 |
|------|------|
| `./openclaw start` | 启动服务（后台） |
| `./openclaw foreground` | 前台运行 |
| `./openclaw stop` | 停止服务 |
| `./openclaw stop-all` | 停止所有实例 |
| `./openclaw restart` | 重启服务 |
| `./openclaw status` | 查看状态 |
| `./openclaw web` | 打开 Web 界面 |

**快捷启动**：macOS 双击 `Start.app`，Windows 双击 `Start.vbs`

---



---

## 🔐 硬件绑定

OpenClaw 采用**硬件指纹绑定**技术，绑定后只能在当前设备运行：

- ✅ 安全性：防止非法复制
- ✅ 便携性：可放入 USB 随身携带
- ✅ 唯一性：每设备独立授权

**绑定信息**：设备序列号 · 存储容量 · 文件系统 UUID
## 📁 目录结构

```
openclaw-portable/
├── openclaw              # 启动器
├── Start.app             # macOS 启动应用
├── Start.command         # macOS 启动脚本
├── Start.vbs             # Windows 启动脚本
├── install.sh            # 安装脚本
├── README.md             # 本文件
│
├── core/
│   ├── openclaw/         # 核心程序
│   ├── openclaw-data/    # 数据目录
│   │   ├── config/       # 配置文件
│   │   ├── logs/         # 日志文件
│   │   └── tmp/          # 临时文件
│   └── public/           # 静态资源
│
└── workspace/            # 工作空间
    ├── AGENTS.md         # 智能体配置
    ├── SOUL.md           # 人格定义
    ├── TOOLS.md          # 工具配置
    ├── USER.md           # 用户信息
    ├── MEMORY.md         # 长期记忆
    └── memory/           # 记忆文件
```

## 🔍 常见问题

### macOS "无法打开" 提示
1. 首次使用双击 `Start.command`
2. 设置 → 隐私与安全性 → 仍要打开
3. 之后可用 `Start.app` 启动

### 无法启动
```bash
# 检查绑定状态
./openclaw status

# 重新安装
./openclaw install

# 查看日志
./openclaw foreground
```

### 端口被占用
```bash
lsof -i :8765          # 查找占用进程
./openclaw stop-all    # 停止所有实例
```

### 复制到其他设备无法运行
> ⚠️ 这是正常的安全机制，硬件绑定后不可跨设备使用

### 查看日志
```bash
cat core/openclaw-data/logs/openclaw.log
./openclaw foreground
```

## 💾 备份与迁移

### 需备份的目录
```
core/openclaw-data/config/    # 配置
core/openclaw-data/logs/      # 日志
workspace/memory/             # 记忆文件
workspace/MEMORY.md           # 长期记忆
```

### 迁移步骤
1. 新设备解压并运行 `./openclaw install`
2. 复制备份数据到新设备对应目录
3. 重启服务

## 🌐 访问地址

```
http://localhost:8765
http://127.0.0.1:8765
```

## 📞 获取

## ⚠️ 注意事项

1. **请勿删除** `.encrypted` 目录，否则软件将无法运行
2. **请勿修改** `core/openclaw/` 目录下的文件
3. **定期备份** `core/openclaw-data/` 和 `workspace/` 目录
4. **硬件绑定后**，复制到其他设备需要重新安装
5. **升级版本**时，建议备份数据后重新解压

---

<p align="center">
  <i>让 AI 随身携带，随时随地为您服务</i>
</p>
