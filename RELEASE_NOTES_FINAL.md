# v0.1.0-oss — First attributed public release candidate

> **Release status:** candidate text only; no GitHub release or tag has been published by this task.

这是 `mgws2/astrbot-plugin-media-parser-enhanced` 的首次衍生开源版本，基于 [drdon1234/astrbot_plugin_media_parser](https://github.com/drdon1234/astrbot_plugin_media_parser) 的公开代码。原作者、AGPL-3.0 及相关第三方许可证/署名予以保留。本仓库**不是上游官方版本**，也不包含生产 QQ 机器人的私有扩展。

## 功能概览

- 提供 B 站、抖音等平台的媒体链接解析模块，支持文本/富媒体输出、消息触发及可配置输出模式。
- 包含部分媒体下载、消息节点、归档与错误回退机制。**具备代码功能不代表各平台当前均能正常在线工作。**

## 已完成验证（2026-10-27）

- 实际独立 AstrBot **4.27.4** / Python **3.12.13**：宿主启动、插件加载、配置初始化和 `auto_parse` 注册 **PASS**。
- B 站公开链接：解析器层在线测试 **PASS**（两次返回非空结果）。未验证 QQ 实际投递。
- 抖音公开链接：新样例解析器层 **PASS**；旧样例 **FAIL**（详情 API HTTP 403，页面回退无有效数据，根因未确定）。未声称已修复。
- 错误回退：在真实 AstrBot 宿主事件配合本地记录器的测试中，四种配置分别发送一条失败文本，没有误发媒体或开场语，**PASS（记录器级别）**。
- 离线回归：Python **3.11**、真实依赖与 AstrBot 测试替身，**53 PASS / 0 FAIL / 16 NOT_APPLICABLE**。

## 已知限制

- **QQ 实际发送、NapCat/OneBot 消息投递未验证**；验证宿主事件并不等于消息真正进入群聊。
- 平台访问受网络、登录限制、HTTP 403/412、接口变动影响，尤其是旧抖音公开示例。不要将平台支持列表理解为在线成功率保证。
- 在“仅富媒体”模式下，即使关闭“显示原始链接”，当前错误文本仍会保留链接；此为观察到的现有行为，非本轮新增功能。
- 本公开仓库**不含**生产私有 Cookie/密钥、QQ 机器人配置、浏览器 sidecar、Worker/R2、私有解析补丁等。

## 安装与问题反馈

请阅读 [README 安装指引](https://github.com/mgws2/astrbot-plugin-media-parser-enhanced#快速安装)，**先在独立 AstrBot 实例验证**，不要直接覆盖已有的生产插件。如遇故障，请在 [Issues](https://github.com/mgws2/astrbot-plugin-media-parser-enhanced/issues) 中提交 AstrBot/Python 版本、脱敏日志、可公开复现的链接和预期/实际结果。

**License:** AGPL-3.0；第三方说明见仓库 NOTICE、CREDITS.md 与 LICENSES/。

内部插件版本 `0.1.0`；`v0.1.0-oss` 是衍生版候选标签。该版本低于遗留 `7.0.0`，已有安装的升级识别尚未验证。
