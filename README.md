# generate-ppt Skill

这是一个给 Codex 使用的 PPT 生成技能，用于把逐字稿、课程稿、文档或参考资料规划并生成图片版 PPT。

## 一键安装

把下面这句话发给 Codex：

```text
请安装这个 skill：
https://github.com/zhengzhentao86/zhentao/tree/main/generate-ppt
```

安装完成后，重启 Codex 或新开一个会话。

## 详细使用说明

请看这里：

[generate-ppt Skill 使用说明](https://github.com/zhengzhentao86/zhentao/blob/main/USAGE.md)

## 最常用提示词

```text
请使用 generate-ppt 技能，把我上传的逐字稿做成图片版 PPT。
先给我完整页面蓝图，不要先生成图片。
每 10-15 页安排一个容易传播的金句页，不要全是技术流程。
蓝图里要包含：页码、页面类型、页面主句、辅助文字、图形表达、来源依据。
```

## 这个 skill 会做什么

- 把逐字稿、课程稿、Word、PDF、Markdown 等材料规划成 PPT 页面。
- 默认做图片版 PPT，每页是一张完整 16:9 幻灯片。
- 每页包含主句/标题、辅助文字、图形结构或插图。
- 每 10-15 页安排一个传播金句页，避免整套 PPT 全是技术内容。
- 先出页面蓝图，再出样张，确认后批量生成整套 PPT。

## 手动安装目录

Windows：

```text
%USERPROFILE%\.codex\skills\generate-ppt\SKILL.md
```

macOS / Linux：

```text
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

## 注意

- 不是把 zip 或链接发给 Codex 就自动生效；需要明确说“请安装这个 skill”。
- 安装后通常需要重启 Codex 或新开会话。
- 如果要读取飞书/Lark 文档，本机还需要配置好 `lark-cli`；否则建议先把文档导出为 Word、PDF 或 Markdown 再给 Codex。
