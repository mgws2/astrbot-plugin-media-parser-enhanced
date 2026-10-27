# AstrBot Media Parser Enhanced

> 在 AstrBot 群聊中解析多平台媒体链接，按需输出文本、图片和视频。
>
> Community-maintained, attributed distribution of [AstrBot Media Parser](https://github.com/drdon1234/astrbot_plugin_media_parser).

[![AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue)](LICENSE)
[![AstrBot 4.x](https://img.shields.io/badge/AstrBot-%3E%3D4%2C%3C5-6C57FF)](metadata.yaml)
[![Python 3.11 offline tested](https://img.shields.io/badge/Python-3.11%20offline--tested-3776AB)](requirements.txt)
[![Issues](https://img.shields.io/github/issues/mgws2/astrbot-plugin-media-parser-enhanced)](https://github.com/mgws2/astrbot-plugin-media-parser-enhanced/issues)

**中文** · [English](#english-overview) · [安装](#快速安装) · [贡献](CONTRIBUTING.md) · [许可](#原作者与许可证)

基于 **[drdon1234/astrbot_plugin_media_parser](https://github.com/drdon1234/astrbot_plugin_media_parser)** 的衍生版本，保留上游原作者和 AGPL-3.0 许可证。此仓库分享可再发行的公开代码，**不是**腾讯云 QQ 机器人生产环境的完整备份。

## ✨ 主要功能

| 功能 | 说明 |
| --- | --- |
| 🔗 多平台解析 | B 站、抖音、TikTok、快手、微博、小红书、闲鱼、今日头条、小黑盒、Twitter/X、Pixiv 的解析模块 |
| 📨 灵活触发 | 消息链接自动解析；可配置关键词、引用消息触发 |
| 🎛️ 自定义输出 | 各平台可选关闭、全部发送、仅文本、仅富媒体 |
| 📦 群聊友好 | 消息聚合、ZIP 归档、视频封面、元数据字段、频率限制 |
| 🧩 附加内容 | 支持的平台可配置热评，实际结果依赖平台接口 |

> **包含解析模块不代表所有平台当前均可用。** 登录权限、访问环境、平台 API 和机器人适配器都会影响成功率。本文不将离线测试宣传为真实平台验收。

**消息流程：** 群聊链接 → AstrBot 插件 → 平台解析器 → 下载/消息处理 → 摘要与媒体输出。

## 🚀 快速安装

**环境：** 插件元数据声明 AstrBot 4.x（>=4,<5）。Python 及依赖应安装在 AstrBot 的实际宿主环境中；部分媒体处理需要另行安装 FFmpeg。

1. 从 [GitHub 下载 ZIP](https://github.com/mgws2/astrbot-plugin-media-parser-enhanced/archive/refs/heads/main.zip) 并解压。
2. 将目录重命名为 **astrbot_plugin_media_parser**，放在 AstrBot 的 **data/plugins/** 下。
3. 按 AstrBot 的安装方式，在其运行的 Python 环境安装 [requirements.txt](requirements.txt) 依赖。
4. 正常加载插件，在 AstrBot 插件配置页设置各平台的触发和输出模式；配置结构见 [_conf_schema.json](_conf_schema.json)。
5. 先用无需登录的公开链接测试；发生失败时检查脱敏后的日志、平台访问条件及适配器媒体发送能力。

**请先在测试实例中安装，不要覆盖正常运行的生产机器人。** Cookie、Token、私人配置及群聊记录不得提交至公开仓库。

## ✅ 当前验证范围

| 项目 | 状态 |
| --- | --- |
| Python 语法 / 相对导入 | 67 个文件语法通过；191 处导入引用检查通过 |
| 离线测试 | **53 PASS / 0 FAIL**（2026-10-27，AstrBot 宿主使用测试替身） |
| 公开源码 / 候选 ZIP 敏感扫描 | 通过限定规则扫描 |
| 真实 AstrBot 启动、QQ 收发、平台在线解析 | **尚未完整验证** |
| 抖音浏览器侧车、私有 Worker、生产专用修复 | **未包含** |

公开版基于上游 [c16a938](https://github.com/drdon1234/astrbot_plugin_media_parser/commit/c16a938128014403057f1deeeaedecbd1fc15707)。其中 B 站 AV→BV 转换函数采用带 MIT 署名的参考实现局部适配。B 站仍可能遇到 HTTP 412；某些错误诊断包含远端响应文本片段，公开日志前务必脱敏。真实功能是否可用以用户实际环境为准。

## 🤝 问题反馈与维护

欢迎提交兼容性反馈和最小修复：

- [提交 Issue](https://github.com/mgws2/astrbot-plugin-media-parser-enhanced/issues/new/choose)
- [阅读贡献指南](CONTRIBUTING.md)
- [查看变更记录](CHANGELOG.md)

报告问题时，请附 AstrBot/Python 版本、涉及平台、预期与实际结果，以及**脱敏**日志；无需上传真实 Cookie、群聊信息或私人媒体链接。维护优先围绕实际用户反馈推进，不虚构 Star、下载量或社区使用记录。

## 📜 原作者与许可证

- 原项目：[drdon1234/astrbot_plugin_media_parser](https://github.com/drdon1234/astrbot_plugin_media_parser)。保留原作者信息；本仓库不是原项目官方替代品。
- 主许可证：[AGPL-3.0](LICENSE)；请保留来源和相应授权义务。
- Colerar/abv 的 MIT 局部实现与抖音 F2 来源等信息见 [NOTICE](NOTICE)、[CREDITS.md](CREDITS.md) 和 [LICENSES/](LICENSES/)。

使用时请尊重内容平台的服务条款、访问限制及著作权。本项目与 AstrBot、Bilibili、抖音、TikTok 和 OpenAI 官方均无隶属或背书关系。

## English overview

An **attributed modified distribution** of [drdon1234/astrbot_plugin_media_parser](https://github.com/drdon1234/astrbot_plugin_media_parser) for AstrBot 4.x. Includes configurable parsing modules for 11 platforms, chat triggers, text/media output and rate controls.

**Verification:** 53 offline cases passed on 2026-10-27 with real Python dependencies and explicit AstrBot host substitutes. Live platform parsing, QQ delivery and host lifecycle **have not** been fully verified for this public snapshot. Browser sidecar and private production extensions are excluded.

Read the [installation guide](#快速安装), [contribution guide](CONTRIBUTING.md), and [license notices](NOTICE).
