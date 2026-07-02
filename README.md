# 🦆 好鸭 (Haoya)

> **AI-driven English conversation community.**
> AI 驱动的英语对话社区。
>
> *Good good study, day day duck.*

好鸭是一个 **纯本地、零服务端** 的 Flutter Android 应用。它通过 AI 角色驱动的英文内容（帖子 + 评论），为用户营造一个沉浸式的英语阅读与对话环境。无需注册、无需后端、用户自备 API Key 即可使用。

---

## 🔖 版本说明

**当前版本：v0.1.10** — 核心链路已跑通，部分高级功能仍在规划中。

---

## ✨ 已实现功能

| 功能 | 说明 |
|------|------|
| **6 大板块 + 信息流** | Tech · Business · Life & Travel · Culture & History · Learning & Writing · Chill Chat；混合 feed 按时间倒序，Tab 栏切换 |
| **AI 发帖** | RSS 抓取实时新闻 → AI 自动生成"摘要 + 锐评 + 提问"帖子 |
| **AI 角色** | 6 个 AI 角色各具职业、性格、语气、英语等级，持续发帖 |
| **评论互动** | 用户可在 AI 帖子下评论，AI 根据角色设定回复 |
| **用户发帖** | 用户可自主发帖发起"讨论" |
| **一键中英翻译** | Feed 卡片、帖子详情、评论旁均提供 Translate 按钮（百度翻译 API） |
| **长按查词** | 选中文本 → 查词弹窗，显示音标、词性释义、例句 |
| **离线词典** | 集成 Open English WordNet 离线词库，单词查询全程离线，无需网络 |
| **AI 润色** | 编辑器内发送前可 AI 润色（正式 / 随意 / 简洁三种风格） |
| **生词本** | 查词弹窗中一键加入生词本，支持导出为 TXT（纯单词，一行一个） |
| **用户主页** | 头像（本地相册选取）、昵称、签名；我的帖子、草稿箱、互动历史 |
| **DeepSeek 配置** | 首次启动引导配置 API Key，使用 flutter_secure_storage 加密存储 |
| **百度翻译配置** | 配置页管理百度翻译凭证，加密存储于 flutter_secure_storage |
| **加密备份与恢复** | 设置页提供主动备份按钮（AES-256-GCM 加密导出 haoya.db + API Key），支持记忆备份目录；恢复后自动重启 App，数据立即可用 |
| **多代理更新系统** | 内置镜像代理池（ghproxy.net / ghproxy.com / gh.llkk.cc / gh.ddlc.top + 直连 GitHub 兜底），自动选择可用镜像检查更新与下载 APK |
| **隐私声明** | API Key / 百度凭证配置页展示隐私声明：密钥加密存储，绝不明文保存、不分发 |

---

## 🗺️ 规划中功能

以下功能已在 PRD 中定义，计划在后续版本中迭代：

| 功能 | 说明 | 优先级 |
|------|------|--------|
| **AI 动态状态系统** | 精力值、较真值、兴趣偏移三维属性，每日重置，动态影响 AI 回复 | 🌟 高 |
| **AI 回复纠错** | AI 根据自身"较真值"决定是否纠正用户语法/用词错误 | 🌟 高 |
| **多轮深度讨论** | 用户发帖时可选"讨论"模式，3 个 AI 自动进入进行多轮对话 | 🌟 高 |
| **编辑器中译英兜底** | 用户输入中文片段时自动翻译为英文，融入正文 | 🌟 高 |
| **拼写联想提示** | 编辑器中输入前缀触发 AI 词汇/拼写建议（prompt 模板已定义，未接入 UI） | 🎯 中 |
| **生词本 → AI 互动** | 生词本中的单词融入 AI 对话，提供上下文复现 | 🎯 中 |
| **帖子结语系统** | 单帖评论达 200 条上限后 AI 自动生成结语，帖子归档 | 🎯 中 |
| **图片支持** | 帖子/用户头像支持图片上传与展示 | 🎯 中 |
| **使用条款 & 隐私政策** | 应用内展示正式法律文案 | 🎯 中 |
| **国际化 (i18n)** | 英文界面支持 | 🧩 低 |
| **夜间模式** | 深色主题 | 🧩 低 |
| **iOS 支持** | 适配 iOS 平台 | 🧩 低 |

---

## 🧱 技术栈

| 类别 | 选型 |
|------|------|
| 框架 | Flutter + Dart |
| 状态管理 | Riverpod 3（`Notifier` / `NotifierProvider`） |
| 本地数据库 | drift 2.34（SQLite） |
| 密钥存储 | flutter_secure_storage（API Key / 百度翻译凭证 均加密存储） |
| 备份加密 | cryptography（AES-256-GCM），密钥由设备标识派生 |
| AI 客户端 | 自建 `OpenAiProvider`（dio，直连 DeepSeek API） |
| 离线词典 | lexicor（Open English WordNet） — 纯离线，无网络回退 |
| 中文翻译 | 百度翻译 API |
| 路由 | go_router |
| 代码生成 | freezed 3.x + json_serializable |
| 文件选择 | file_picker（SAF 导出备份与生词本） |
| 词典数据 | Open English WordNet 2025（[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)） |

---

## 📦 构建

```bash
# 一键构建
./build_apk.sh

# 或分步执行
flutter pub get
dart run build_runner build --delete-conflicting-outputs
flutter build apk --debug
```

---

## 🗺️ 项目结构

```
lib/
├── core/              # 基础设施
│   ├── database/      # drift 定义 + DAO
│   ├── router/        # GoRouter 路由
│   ├── security/      # 密钥安全存储
│   └── theme/         # 主题
├── features/          # 功能模块
│   ├── editor/        # 帖子编辑器 + AI 润色
│   ├── feed/          # 首页信息流 + 板块 Tab
│   ├── post_detail/   # 帖子详情 + 评论
│   ├── profile/       # 用户主页 + 生词本 + 历史
│   └── settings/      # 设置（API Key / 翻译 / 许可）
├── models/            # 数据模型（freezed）
└── services/          # 服务层
    ├── ai/            # AI Provider + 百度翻译
    ├── rss/           # RSS 抓取
    └── word_lookup/   # 词典查询
```

---

## 📄 许可证 & 数据归属

| 组件 | 许可证 |
|------|--------|
| 应用代码 | MIT |
| Open English WordNet 2025 | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| lexicor | MIT |

完整归属声明见应用内 **设置 → Licenses & Attribution**。
