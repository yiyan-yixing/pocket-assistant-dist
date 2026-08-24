# Changelog

All notable changes to 口袋助手 (Pocket Assistant) are documented in this file.

## [0.1.0] - 2026-08-24

### MVP P0 · 灰度发布

**本地离线**
- 内置 Qwen2.5-1.5B 本地模型（GGUF Q4_K_M），飞行模式 / 断网可离线对话
- 模型「就绪前」全链路体验：未就绪发消息给可见中文引导，首启/重启自动加载 + 进度/阶段展示

**云端按需**
- BYO Key：直连任意 OpenAI 兼容网关（baseUrl + API key + 模型名），引擎一键切换
- Key 迁入系统安全存储（iOS Keychain / Android Keystore），旧明文一次性迁移后清除

**工具闭环**
- 位置 / 天气 / 搜索三工具端到端可用，工具层抽象纯 Dart 不绑推理引擎
- 搜索在内置 WebView 完成（JS 注入抓取结果文本回填，模型基于真实结果收尾）
- 触发词兜底 + 日期/时间/星期程序注入 + 人设统一答复

**安全与合规**
- 对话历史 SQLite 本地存储，数据不出机；云端请求有「云端」来源标签
- AI 生成内容声明 + 模型衍生说明（Apache 2.0）+ 商标免责声明

### 已知限制
- 意图识别粒度较粗（1.5B 能力边界），第二期做技能化意图路由或模型升级
- iOS（缺 Xcode 后置）、HarmonyOS NEXT（P1 后置）
- 云端为纯对话骨架（不带工具），双引擎统一工具循环第二期
