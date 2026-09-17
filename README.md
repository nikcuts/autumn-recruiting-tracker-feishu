# 秋招进度与飞书同步 Skill

用自然语言记录秋招投递、测评、笔试和面试，并同步到你自己授权的飞书多维表格与飞书日历。

## 能做什么

- 首次使用时引导安装飞书官方 CLI、完成授权、选择或创建 Base 和目标表。
- 用一句话新增或更新公司、岗位、地点、状态、投递日期、JD 和链接。
- 将明确的测评、笔试、面试时间写入飞书日历，并避免重复日程。
- 只读检查未来日程冲突、临近事项和投递停滞情况。
- 用户提供 JD 时，提炼职责、技术要求、缺口和准备重点。

本项目不会替你登录招聘网站、完成笔试测评，也不会保存你的 access token、密码或验证码。

## 安装

1. 在 Codex 中安装本仓库的 Skill（可使用内置 Skill Installer，仓库路径为 `skills/autumn-recruiting-tracker`）。
2. 或将 `skills/autumn-recruiting-tracker` 目录复制到本机的 `$CODEX_HOME/skills/`。
3. 对 Codex 说：`使用 autumn-recruiting-tracker 帮我配置秋招记录。`
4. 按首次设置向导完成飞书授权。授权页面必须由你本人确认。

飞书 CLI 使用官方项目 [larksuite/cli](https://github.com/larksuite/cli)。Skill 会优先使用用户身份（`--as user`）访问个人资源。

## 首次设置

首次使用会询问飞书/Lark、已有 Base 或新建 Base、目标表、飞书日历以及提醒偏好。默认只启用飞书 Base 和飞书日历；本地日历、邮箱监控等可选能力不会阻塞核心设置。

macOS 用户可以在完成核心设置后，按 [macOS 可选模块](skills/autumn-recruiting-tracker/references/macos.md) 启用 Calendar 同步和 Mail.app 招聘邮件只读监控。模块会先发现本机账户和日历并让用户选择，不会使用仓库作者的个人配置。

表格至少需要公司、岗位、工作地点、投递日期、投递链接、投递进度、笔面试提醒和招聘信息等字段。修改已有表结构前，Skill 会先展示差异并等待确认。

可参考 [首次设置向导](skills/autumn-recruiting-tracker/references/setup.md) 和 [示例配置](skills/autumn-recruiting-tracker/assets/config.example.json)。

## 示例对话

```text
我今天投递了某公司 AI 应用工程师，base 北京，链接是……
把某公司的线上笔试安排在 9 月 28 日 19:00–21:00。
帮我检查未来三天的秋招日程有没有冲突。
总结这个岗位 JD，并告诉我面试前优先准备什么。
```

## 隐私与权限

- 仓库只包含通用规则和示例，不包含任何个人投递记录。
- `config.local.json` 只应保存在本机，已被 `.gitignore` 排除。
- 不要把 Base token、app secret、邮箱密码、验证码或招聘网站账号密码提交到 GitHub。
- 飞书授权范围应按实际需要授予；默认不接入本地邮箱和本地日历。
- 邮件监控（如用户自行启用）只读，并在发现招聘邮件后先通知用户。
- 日程同步只写入用户明确授权的日历；Skill 不会擅自删除、移动或改期。
- macOS 定时巡检只有在用户明确确认后才创建；没有新招聘邮件或需要处理的变化时保持安静。

详细说明见 [PRIVACY.md](PRIVACY.md)。

## 适用范围

这是一个 Codex Skill 模板，不是独立运行的招聘网站机器人。实际能力取决于当前 Codex 环境、飞书 CLI 版本、授权范围以及可用的日历连接器。

## License

MIT
