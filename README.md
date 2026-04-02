# Meeting Guide

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome">
  <img src="https://img.shields.io/badge/Trae%20Skill-compatible-orange" alt="Trae Skill">
</p>

<p align="center">
  <b>会议概览总结生成工具</b><br>
  根据会议录音和照片，一键生成精美的会议汇报网页
</p>

---

## ✨ 功能特性

- 🤖 **AI 智能分析** - 自动解析会议纪要，提取核心观点
- 🎨 **多主题模板** - 支持多种风格的汇报页面主题
- 📸 **照片展示** - 自动生成照片墙和灯箱浏览
- 🎵 **音频播放** - 内置音频播放器，支持会议录音回放
- 📱 **响应式设计** - 完美适配桌面和移动设备
- 🔄 **一键生成** - 简单指令即可完成全部工作

## 📁 项目结构

```
meeting-guide/
├── .trae/
│   └── skills/
│       └── meeting-master/          # Trae Skill 核心代码
│           ├── assets/
│           │   └── themes/          # 主题模板库
│           │       ├── default/     # 默认主题
│           │       │   ├── data.js
│           │       │   └── template.html
│           │       └── tech-conference/  # 科技发布会主题
│           │           ├── data.js
│           │           └── template.html
│           └── references/          # 参考文档
│               ├── data-structure.md
│               └── md-format.md
│
└── mettings/                        # 会议数据示例
    └── demo/
        ├── audios/                  # 录音和纪要文件
        │   ├── 1-河南旅游景点推荐.md
        │   ├── 1-河南旅游景点推荐.mp3
        │   └── ...
        ├── photos/                  # 会议照片
        │   └── ...
        └── result/                  # 生成的汇报页面
            ├── data.js
            └── index.html
```

## 🚀 快速开始

### 方式一：作为 Skill 使用（推荐）

1. 将本项目克隆到本地：
```bash
git clone https://github.com/yourusername/meeting-guide.git
```

2. 加载 Skill：选择 `.trae/skills/meeting-master` 目录
   
3. 使用指令：
   - `/meeting-guide <文件夹路径>` - 根据会议资料生成汇报网页
   - `/meeting-new-template` - 创建自定义主题模板

### 方式二：在 Trae 中直接使用

1. 在 Trae 中打开本项目
2. 准备会议资料：
   - 在 `audios` 目录放置 `.md` 纪要文件和对应的 `.mp3` 录音
   - 在 `photos` 目录放置会议照片
3. 直接告诉 AI 你的需求，如："帮我生成会议汇报页面"
4. AI 会自动读取项目结构并生成汇报网页

## 📝 数据格式

### MD 文件格式

每个 MD 文件包含速览，纪要非必须，缺失时会自动生成：

```markdown
# 速览

00:00
第一段转写内容...

00:45
第二段转写内容...

# 纪要

## 章节标题

- **要点1**：详细说明
- **要点2**：详细说明
```

### 文件命名规范

- 音频文件：`1-会议内容.mp3`
- MD 文件：`1-会议内容.md`
- 确保文件名一致（仅扩展名不同）

## 🎨 主题定制

### 现有主题

| 主题 | 风格 | 适用场景 |
|------|------|----------|
| default | 简洁专业，蓝色系 | 正式会议、培训汇报 |
| tech-conference | 科技感，深色模式 | 技术发布会、产品演示 |

### 创建新主题

使用 `/meeting-new-template` 指令，根据需求创建自定义主题：

1. 描述你想要的风格和场景
2. AI 会基于默认主题生成新的样式
3. 新主题自动注册到主题库

### 主题文件结构

```
themes/{theme-id}/
├── data.js          # 数据文件（保持结构不变）
└── template.html    # HTML 模板（可自定义样式）
```

## 📊 生成页面预览

生成的汇报页面包含以下模块：

- **概览区** - 会议基本信息、议题列表、核心总结
- **照片墙** - 会议照片展示，支持灯箱浏览
- **录音区** - 音频播放器，支持播放和下载
- **时间线** - 按议题组织的会议时间线
- **嘉宾介绍** - 演讲嘉宾信息展示

默认主题：

<img src="pics\default.jpg" style="zoom: 33%;" />

科技风主题：

<img src="pics\tech.jpg" style="zoom:33%;" />

## 🔧 技术栈

- **前端框架**: 原生 HTML + Tailwind CSS
- **样式方案**: Tailwind CSS CDN
- **图标库**: Font Awesome / Heroicons
- **字体**: Noto Sans SC
- **构建工具**: 无需构建，纯静态页面

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

### 提交新主题

1. 在 `assets/themes/` 下创建新主题文件夹
2. 复制 `default` 主题的 `data.js` 和 `template.html`
3. 修改 `template.html` 的样式
4. 在 `themes.json` 中注册新主题
5. 提交 PR

### 代码规范

- 保持 `data.js` 的数据结构不变
- 主题样式使用 Tailwind CSS
- 确保响应式设计
- 添加必要的注释

## 📄 许可证

[MIT License](LICENSE)

## 🙏 致谢

- [Tailwind CSS](https://tailwindcss.com/) - 优秀的 CSS 框架
- [Trae IDE](https://www.trae.ai/) - AI 驱动的 IDE

---

<p align="center">
  如果这个项目对你有帮助，请给个 ⭐ Star！
</p>
