# Mem-Lexis 英语学习 + 电子宠物养成平台

[English](#english) | [中文](#中文)

---

## English

### Overview

Mem-Lexis is a gamified English learning platform that combines vocabulary learning with a virtual pet养成 (raising) system. Users feed and grow their pets by completing daily learning tasks, making the learning process engaging and rewarding.

### Features

- **Smart Assessment**: AI-powered ability assessment generates personalized radar charts
- **Virtual Pet System**: Raise your unique pet - feed, walk, and study together
- **Spaced Repetition**: Built-in Ebbinghaus forgetting curve algorithm for optimal review timing
- **Multi-Exam Support**: CET-4, CET-6, 考研 (Postgraduate), TOEFL, IELTS word banks
- **Offline Dictionary**: Local word lookup with pronunciation support
- **Progress Tracking**: Daily check-in streaks, mastery statistics, and learning analytics

### Tech Stack

- Pure HTML5 + CSS3 + Vanilla JavaScript (single file, no framework)
- IndexedDB for local storage
- Web Speech API for pronunciation
- Google Fonts (Noto Sans SC, Nunito)

### Quick Start

1. Clone the repository
2. Serve with any HTTP server (required for word bank loading):

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

3. Open `http://localhost:8080` in your browser

### Project Structure

```
lingo_pet/
├── index.html          # Main application (HTML + CSS + JS)
├── word-roots.js       # Word roots dictionary
├── words_cet4.json     # CET-4 word bank (4543 words)
├── words_cet6.json     # CET-6 word bank (2165 words)
├── words_kaoyan.json   # 考研 word bank (5304 words)
├── words_toefl.json    # TOEFL word bank (4516 words)
├── words_ielts.json    # IELTS word bank (4516 words)
├── SPEC.md             # Project specification
├── README.md           # This file
└── PRD.md              # Product Requirements Document
```

### Word Bank Architecture

Word banks are split by exam type for faster initial loading:

| File | Words | Size |
|------|-------|------|
| words_cet4.json | 4,543 | ~578KB |
| words_cet6.json | 2,165 | ~350KB |
| words_kaoyan.json | 5,304 | ~743KB |
| words_toefl.json | 4,516 | ~631KB |
| words_ielts.json | 4,516 | ~631KB |

Words are loaded on-demand when users switch exams.

### License

MIT License

---

## 中文

### 项目简介

Mem-Lexis 是一个融合了电子宠物养成机制的英语学习平台。用户通过每日学习打卡来喂养和培养自己的小宠物，宠物的成长状态与学习进度绑定。学习不再是枯燥的任务，而是充满成就感的养成体验。

### 核心功能

- **AI 能力测评**: 通过测试生成能力雷达图，个性化展示词汇、听力、口语、阅读、写作能力
- **电子宠物养成**: 随机生成可爱宠物，喂养、互动、遛宠物，与学习联动
- **艾宾浩斯记忆法**: 科学安排复习时间，遵循遗忘曲线规律
- **多考试词库**: 支持四级、六级、考研、托福、雅思词库，按需加载
- **离线词典**: 本地单词查询，支持发音
- **进度追踪**: 每日打卡、连续天数、掌握度统计

### 技术栈

- 纯 HTML5 + CSS3 + 原生 JavaScript（单文件，无框架依赖）
- IndexedDB 本地存储
- Web Speech API 发音
- Google Fonts (Noto Sans SC, Nunito)

### 快速开始

1. 克隆仓库
2. 使用 HTTP 服务器运行（词库文件需要通过 HTTP 服务加载）:

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

3. 浏览器打开 `http://localhost:8080`

### 部署到 GitHub Pages

1. 推送代码到 GitHub 仓库
2. 进入 Settings → Pages
3. Source 选择 `main` 分支
4. 访问 `https://your-username.github.io/mem-lingo/`

### 项目结构

```
lingo_pet/
├── index.html          # 主应用（HTML + CSS + JS）
├── word-roots.js       # 词根词典
├── words_cet4.json     # 四级词库 (4543词)
├── words_cet6.json     # 六级词库 (2165词)
├── words_kaoyan.json   # 考研词库 (5304词)
├── words_toefl.json    # 托福词库 (4516词)
├── words_ielts.json    # 雅思词库 (4516词)
├── SPEC.md             # 项目详细规格
├── README.md           # 项目介绍
└── PRD.md              # 产品需求文档
```

### 词库分割说明

词库按考试类型分割，实现按需加载：

| 文件 | 单词数 | 大小 |
|------|--------|------|
| words_cet4.json | 4,543 | ~578KB |
| words_cet6.json | 2,165 | ~350KB |
| words_kaoyan.json | 5,304 | ~743KB |
| words_toefl.json | 4,516 | ~631KB |
| words_ielts.json | 4,516 | ~631KB |

切换考试时异步加载对应词库，初始页面只加载当前考试词库，大幅提升首屏速度。

### 许可证

MIT License