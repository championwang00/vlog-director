# race-vlog-director

把比赛、旅行或活动的实拍素材剪成 1–3 分钟社交媒体短片的 Agent Skill。整个流程分三段，由三个 AI 分工完成：

1. **GPT（Codex CLI）理解素材**：生成「素材时间线」网页，写清每份素材的画面、原声转写、所属阶段，并标出主线候选。
2. **Claude 分镜导演**：先交一份「分镜理解稿」给用户确认或调整，然后写剧本，做可播放的分镜预演，按真实节拍对齐音乐，设计音效、转场、花字等包装。
3. **Codex 在剪映里剪辑，Claude 逐轮验收**：Claude 写交接包、调度 Codex，每轮抽帧听音审片。最后交付旁白录音清单、封面和发布文案。

沉淀自一个真实项目：63 份素材剪成约 3 分钟的竖屏成片，Codex 跑了 11 轮。

## 文件
- `SKILL.md`：流水线总览、角色分工、各阶段之间的检查点
- `references/stage1-material-understanding.md`：给 GPT 的任务说明模板、`media-data` 字段规范、Claude 验收步骤
- `references/stage2-storyboard.md`：剧本结构、原声定位、预演网页、音乐对齐手法、包装设计
- `references/stage3-codex-and-review.md`：Codex 启动和接续命令、交接包格式、审片清单
- `references/lessons.md`：踩过的坑和用户偏好
- `references/qiandaohu-case.md`：完整案例
- `references/voiceover-list-template.md`：旁白录音清单模板

## 依赖
Claude Code、Codex CLI（以及 Codex 侧的剪映执行技能 `xhs-jianying-edit`）、剪映专业版、ffmpeg、Whisper；大字卡配合 [eva-typography](https://github.com/championwang00/eva-typography) 使用。

## 安装
```bash
git clone https://github.com/championwang00/race-vlog-director ~/.claude/skills/race-vlog-director
```
