# generate-ppt Skill

这是一个给 Codex 使用的 PPT 生成技能，用于把逐字稿、课程稿、文档或参考资料规划并生成图片版 PPT。

## 一键让 Codex 安装

把下面这句话发给你电脑上的 Codex：

```text
请安装这个 skill：
https://github.com/zhengzhentao86/zhentao/tree/main/generate-ppt
```

安装完成后，重启 Codex 或新开一个会话。

## 手动安装

如果 Codex 没有自动安装成功，可以手动下载仓库，然后把 `generate-ppt` 文件夹放到你的 Codex skills 目录。

Windows 默认目录：

```powershell
%USERPROFILE%\.codex\skills\generate-ppt\SKILL.md
```

macOS / Linux 默认目录：

```bash
~/.codex/skills/generate-ppt/SKILL.md
```

最终结构必须是：

```text
.codex/
  skills/
    generate-ppt/
      SKILL.md
      agents/
        openai.yaml
```

## 使用方式

安装并重启 Codex 后，可以这样说：

```text
请使用 generate-ppt 技能，把我上传的逐字稿做成图片版 PPT。
先给我完整页面蓝图，不要先生成图片。
每 10-15 页安排一个容易传播的金句页，不要全是技术流程。
蓝图里要包含：页码、页面类型、页面主句、辅助文字、图形表达、来源依据。
```

如果想直接生成完整 PPT，可以说：

```text
请使用 generate-ppt 技能，把这份逐字稿直接生成完整图片版 PPT。
每页用 Image 2 生成完整 16:9 幻灯片，不要只生成背景。
每 10-15 页安排一页传播金句，不要全是技术。
生成后组装成 PPTX，并给我图片目录和总览图。
```

## 注意

- 不是把 zip 或链接发给 Codex 就自动生效；需要明确说“请安装这个 skill”。
- 安装后通常需要重启 Codex 或新开会话。
- 如果要读取飞书/Lark 文档，本机还需要配置好 `lark-cli`；否则建议先把文档导出为 Word、PDF 或 Markdown 再给 Codex。
