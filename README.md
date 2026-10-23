# My Codex Skills

个人 Codex 技能集合，包含 7 项技能及其配套脚本、参考资料、模板和图片资源。

| 目录 | 技能名称 | 用途 |
| --- | --- | --- |
| [anti-defensive-writing](anti-defensive-writing/SKILL.md) | anti-defensive-writing | 学术叙事与表达优化，减少防御性写作 |
| [citation-management](citation-management/SKILL.md) | citation-management | 文献检索、引文核验、BibTeX 和参考文献格式管理 |
| [gpt-image2-ppt-skills](gpt-image2-ppt-skills/SKILL.md) | gpt-image2-ppt | 使用图像生成制作 PPT，支持风格库和模板仿作 |
| [literature-review](literature-review/SKILL.md) | literature-review | 系统性文献检索、筛选、评价与综述 |
| [patent-drafting](patent-drafting/SKILL.md) | patent-drafting | 中文专利交底、权利要求、说明书与审查修改 |
| [peer-review](peer-review/SKILL.md) | peer-review | 科研论文评审、实验设计检查与审稿回复支持 |
| [scientific-writing](scientific-writing/SKILL.md) | scientific-writing | 中英文科研论文写作、修改及 LaTeX 内容组织 |

科研类技能主要面向自动驾驶、智能交通、机器人与 AI 相关研究。

## 安装

将需要的技能目录复制到个人技能目录。本机使用的目录为 Windows 下的 `%USERPROFILE%\.codex\skills`，其他平台可使用 `~/.codex/skills`。

例如，在 PowerShell 中安装科学写作技能：

```powershell
git clone https://github.com/SafeDL/mycodexskills.git
$destination = Join-Path $env:USERPROFILE '.codex\skills'
New-Item -ItemType Directory -Path $destination -Force | Out-Null
Copy-Item -LiteralPath '.\mycodexskills\scientific-writing' -Destination $destination -Recurse -Force
```

每个技能以自身的 `SKILL.md` 为入口；运行依赖和使用方式见对应技能文档。保留完整目录，以便脚本、参考资料和资源之间的相对路径正常工作。

## 同步范围

本仓库收录个人独立技能，不包含 Codex 的 `.system` 系统技能、插件缓存或账户凭据。各技能原有的许可证、作者信息及说明保留在对应目录中。
