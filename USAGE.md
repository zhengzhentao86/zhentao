# generate-ppt Skill 使用说明

这份文档写给第一次使用 Codex Skill 的人。照着做即可，不需要懂代码。

## 这是什么

`generate-ppt` 是一个给 Codex 使用的技能。安装后，你可以把逐字稿、课程稿、Word、PDF、Markdown 或其他参考资料交给 Codex，让它按固定流程帮你规划并制作图片版 PPT。

这个 skill 的特点：

- 默认把内容做成可以直接讲课的图片版 PPT。
- 每页不是单纯背景图，而是完整幻灯片：标题、辅助文字、图形结构都在画面里。
- 每 10-15 页会安排一个容易传播的金句页，避免整套 PPT 全是技术步骤。
- 会先规划页面蓝图，再生成样张，再批量生成整套 PPT。

## 最简单的安装方式

打开 Codex，把下面这段话复制进去：

```text
请安装这个 skill：
https://github.com/zhengzhentao86/zhentao/tree/main/generate-ppt
```

Codex 安装完成后，重启 Codex，或者新开一个会话。

## Windows 手动安装方式

如果 Codex 没有自动安装成功，可以按下面步骤手动安装。

### 第 1 步：下载仓库

打开这个链接：

```text
https://github.com/zhengzhentao86/zhentao
```

点击绿色按钮 `Code`，再点 `Download ZIP`。

### 第 2 步：解压 ZIP

下载完成后，把 ZIP 解压出来。

解压后找到这个文件夹：

```text
generate-ppt
```

这个文件夹里面应该有：

```text
generate-ppt\SKILL.md
generate-ppt\agents\openai.yaml
```

### 第 3 步：放到 Codex skills 目录

在 Windows 文件资源管理器地址栏输入：

```text
%USERPROFILE%\.codex\skills
```

如果没有这个目录，就手动新建：

```text
.codex\skills
```

然后把 `generate-ppt` 文件夹放进去。

最终必须是这个结构：

```text
C:\Users\你的用户名\.codex\skills\generate-ppt\SKILL.md
C:\Users\你的用户名\.codex\skills\generate-ppt\agents\openai.yaml
```

注意：不要多套一层目录。错误示例：

```text
C:\Users\你的用户名\.codex\skills\zhentao-main\generate-ppt\SKILL.md
```

### 第 4 步：重启 Codex

安装完成后，关闭 Codex，再重新打开。也可以新开一个会话。

## 怎么确认安装成功

重启后，在 Codex 里输入：

```text
你现在能看到 generate-ppt 这个 skill 吗？如果能，请简单说明它的用途。
```

如果 Codex 能说出它是用来根据逐字稿、课程稿、文档生成图片版 PPT 的，就说明安装成功。

## 第一次使用：推荐提示词

如果你想先看整套 PPT 的规划，不急着生成图片，用这一段：

```text
请使用 generate-ppt 技能，把我上传的逐字稿做成图片版 PPT。
先不要生成图片，先给我完整页面蓝图。

蓝图里要包含：
1. 页码
2. 页面类型
3. 页面主句/标题
4. 辅助文字
5. 图形表达
6. 来源依据

要求：
- 每页都要像可以直接讲课的 PPT 页面，不要只是目录。
- 每 10-15 页安排一个容易传播的金句页。
- 不要全是技术流程，要有观点、有转场、有总结。
- 不要编造文档里没有的数据、政策和案例。
```

如果你想让 Codex 直接生成整套 PPT，用这一段：

```text
请使用 generate-ppt 技能，把这份逐字稿直接生成完整图片版 PPT。

要求：
- 每页用 Image 2 生成完整 16:9 幻灯片。
- 不要只生成背景图。
- 页面里必须包含主句/标题、辅助文字、图形结构或插图。
- 每 10-15 页安排一页传播金句。
- 不要全是技术步骤，要把技术内容翻译成学员听得懂的观点。
- 生成后组装成 PPTX，并给我图片目录和总览图。
```

## 推荐工作流程

### 1. 先上传材料

可以上传这些材料：

- 逐字稿
- 课程稿
- Word 文档
- PDF
- Markdown
- 旧 PPT
- 参考图片
- 已经满意的 PPT 样例

如果资料很多，建议先告诉 Codex：

```text
我会先上传资料，你先阅读和理解，不要马上生成 PPT。
```

### 2. 让 Codex 先出页面蓝图

页面蓝图就是整套 PPT 的剧本。先确认蓝图，可以减少后面返工。

重点看这几件事：

- 页数是否合适。
- 叙事顺序是否顺。
- 每页主句是不是像 PPT 标题，而不是普通目录。
- 金句页是否真的有传播感。
- 有没有编造材料里没有的信息。

### 3. 先生成 1 页样张

蓝图确认后，让 Codex 先生成一页代表性样张：

```text
蓝图可以。请先用 Image 2 生成第 3 页样张，不要批量生成。
```

如果样张风格满意，再继续：

```text
这个风格可以，继续按这个风格生成剩余页面。
```

如果不满意，可以直接指出问题：

```text
这个太技术文档了，不像课程 PPT。请增加视觉层级，主句更大，图形更有传播感，再重做样张。
```

### 4. 批量生成整套 PPT

样张确认后，Codex 会逐页生成图片，并最终组装成 PPTX。

交付时应该拿到：

- `.pptx` 成品文件
- 每页图片目录
- contact sheet 总览图
- 哪些页生成或替换过的说明

## 常见问题

### 1. 我把链接发给 Codex 了，为什么没生效？

要明确说“请安装这个 skill”。只发链接不一定会自动安装。

正确说法：

```text
请安装这个 skill：
https://github.com/zhengzhentao86/zhentao/tree/main/generate-ppt
```

### 2. 安装了，为什么 Codex 还是不用这个 skill？

通常是没有重启 Codex。安装 skill 后，建议重启 Codex 或新开会话。

也可以在提示词里明确写：

```text
请使用 generate-ppt 技能。
```

### 3. 这个 skill 会自动生成 PPT 吗？

会，但推荐先让它输出页面蓝图。蓝图确认后再生成图片，质量更稳。

如果你明确说“直接生成”“不用确认”“继续生成完整 PPT”，它会进入快速直出模式。

### 4. 它和普通做 PPT 有什么区别？

普通做 PPT 容易变成文字堆砌。这个 skill 会强制按页面来规划：

- 每页有主句。
- 每页有图形表达。
- 每 10-15 页有传播金句。
- 先确认结构，再生成样张，再批量制作。

### 5. 飞书文档能不能直接用？

可以，但电脑上需要配置好 `lark-cli`。如果没有配置，建议先把飞书文档导出为 Word、PDF 或 Markdown，再上传给 Codex。

## 给别人转发的短版说明

你可以直接把下面这段转发给对方：

```text
这是一个 Codex 做 PPT 的 skill。

安装方式：
打开 Codex，输入：
请安装这个 skill：
https://github.com/zhengzhentao86/zhentao/tree/main/generate-ppt

安装后重启 Codex。

使用方式：
上传逐字稿或课程稿，然后输入：
请使用 generate-ppt 技能，把我上传的逐字稿做成图片版 PPT。先给我页面蓝图，每 10-15 页安排一个传播金句页，不要全是技术流程。
```
