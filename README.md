# 🦆 好鸭 (Haoya)

> **AI-driven English conversation community.**
> AI 驱动的英语对话社区。
>
> *Good good study, day day duck.*

好鸭是一个 **纯本地、零服务端** 的 Flutter Android 应用。它通过 AI 角色驱动的英文内容（帖子 + 评论），为用户营造一个沉浸式的英语阅读与对话环境。无需注册、无需后端、用户自备 API Key 即可使用。

---

## 🔖 版本说明

**当前版本：v0.2.1** — AI 评价系统 + 动态状态系统核心逻辑已落地。

---

## ✨ 已实现功能

| 功能 | 说明 |
|------|------|
| **6 大板块 + 信息流** | Tech · Business · Life & Travel · Culture & History · Learning & Writing · Chill Chat；混合 feed 按时间倒序，Tab 栏切换；下拉刷新按时间配额智能生成 |
| **AI 发帖** | RSS 抓取实时新闻（China Daily 6 频道）→ AI 自动生成"摘要 + 锐评 + 提问"帖子；去重 + 按板块分配 AI 角色 |
| **AI 角色** | 6 个 AI 角色各具职业、性格、语气、英语等级（B1-C2），持续发帖；精力/较真/兴趣三维状态影响 AI 回复风格（后端已接入） |
| **评论互动** | 用户可在 AI 帖子下评论，AI 根据角色设定回复（含延迟模拟、精力消耗）；达上限后 AI 自动生成结语 |
| **用户发帖（讨论模式）** | 用户可发起"讨论帖"，系统自动指派 3 个不同英语水平的 AI 角色参与多轮讨论 |
| **一键中英翻译** | Feed 卡片、帖子详情、评论旁均提供 Translate 按钮（百度翻译 API）；支持标题+内容联合翻译 |
| **内容评价（AI 纠错）** | Feed 卡片旁 Review 按钮，LLM 多维分析（词汇、语法、地道程度、优缺点），中文输出摘要+全文；支持重新生成 |
| **长按查词** | 选中文本 → 查词弹窗，显示音标、词性释义、例句；词形还原回退（复数、过去式、ing 等） |
| **离线词典** | 集成 Open English WordNet 离线词库，单词查询全程离线；基于 CEFR 的生词等级标注 |
| **AI 润色** | 编辑器内发送前可 AI 润色（正式 / 随意 / 简洁三种风格），支持预览三选一；自动保存草稿历史 |
| **生词本** | 查词弹窗中一键加入生词本，标注 CEFR 等级，标记已掌握；支持导出为 TXT（纯单词，一行一个） |
| **草稿箱** | 编辑器自动保存草稿历史（原始内容、润色版本、所选风格），可回顾恢复 |
| **用户主页** | 头像（本地相册选取）、昵称、签名（首次启动默认"Good good study, day day duck."）；我的帖子、草稿箱、互动历史、词汇统计面板 |
| **DeepSeek 配置** | 首次启动引导配置 API Key，使用 flutter_secure_storage 加密存储 |
| **百度翻译配置** | 配置页管理百度翻译凭证，支持测试 API 连通性 |
| **加密备份与恢复** | 设置页提供主动备份按钮（加密导出全部数据），支持记忆备份目录；恢复后自动重启 App；更新弹窗内支持一键预备份 |
| **多代理更新系统** | 内置镜像代理池（ghproxy.net / ghproxy.com / gh.llkk.cc / gh.ddlc.top + 直连 GitHub 兜底），自动选择可用镜像检查更新与下载 APK |
| **应用内日志查看器** | 实时查看过滤日志，支持按级别筛选、复制和清空 |
| **开源许可页面** | 应用内展示 Open English WordNet (CC BY 4.0) 等第三方依赖归属 |
| **隐私声明** | API Key / 百度凭证配置页展示隐私声明：密钥加密存储，绝不明文保存、不分发 |

---

## 🗺️ 规划中功能

以下功能已在 PRD 中定义，计划在后续版本中迭代：

| 功能 | 说明 | 优先级 |
|------|------|--------|
| **AI 动态状态系统完善** | 精力/较真/兴趣三维属性每日自动重置，视觉化展示状态标签 | 🌟 高 |
| **AI 回复深度纠错** | 在现有内容评价基础上，AI 在回复中主动纠正用户语法/用词错误 | 🌟 高 |
| **多轮深度讨论完善** | 讨论帖中 AI 间持续多轮互动，用户可参与打断 | 🌟 高 |
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
| 备份加密 | 本地加密备份，设备绑定密钥 |
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
│   ├── editor/        # 帖子编辑器 + AI 润色 + 草稿箱
│   ├── feed/          # 首页信息流 + 板块 Tab + 内容评价
│   ├── post_detail/   # 帖子详情 + 评论
│   ├── profile/       # 用户主页 + 生词本 + 草稿箱 + 历史
│   ├── settings/      # 设置（API Key / 翻译 / 许可 / 日志）
│   └── word_lookup/   # 查词弹窗 + 词典查询
├── models/            # 数据模型（freezed）
└── services/          # 服务层
    ├── ai/            # AI Provider + 百度翻译 + prompt 模板
    ├── rss/           # RSS 抓取
    ├── state/         # AI 动态状态系统 + 互动摘要
    ├── word_lookup/   # 词典查询
    ├── backup_service.dart
    ├── content_evaluation_service.dart
    ├── logger_service.dart
    ├── startup_service.dart
    └── update_service.dart
```

---

## 📄 许可证 & 数据归属

| 组件 | 许可证 |
|------|--------|
| 应用代码 | MIT |
| Open English WordNet 2025 | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| lexicor | MIT |

完整归属声明见应用内 **设置 → Licenses & Attribution**。
