# AI Image Realism Skill

[English](./README.md) | 简体中文

修复 AI 图片的塑料感、手指与面部破绽、重复纹理和光影不协调，尽量保留人物、商品与原有构图，让已选图片更自然可信，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 修复AI图片的塑料感、手指与面部破绽、重复纹理和光影违和，尽量保留人物、商品与原有构图，让已选图片更自然可信。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="一张虚构女性的肖像，为了这个演示特意生成了蜡质皮肤、过饱和的 AI 感，修复后皮肤纹理和光线变得自然，脸、姿势、毛衣和咖啡馆背景都保持不变。由 Beatra AI 生成。"></p>

*一张虚构女性的肖像，为了这个演示特意生成了蜡质皮肤、过饱和的 AI 感，修复后皮肤纹理和光线变得自然，脸、姿势、毛衣和咖啡馆背景都保持不变。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-image-realism`](skills/ai-image-realism) | [SKILL.md](skills/ai-image-realism/SKILL.md) | 0.3.0 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-image-realism) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-image-realism-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-image-realism-skill ai-image-realism
```

也可以克隆本仓库，把 `skills/ai-image-realism` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-image-realism-skill 安装 ai-image-realism skill（目录 skills/ai-image-realism），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/demo-2.webp" width="800" alt="同一张脸修复前后的特写：磨皮般的皮肤和两团圆形橙色腮红，换成了看得见毛孔的皮肤和自然的红润。由 Beatra AI 生成。"></p>

*同一张脸修复前后的特写：磨皮般的皮肤和两团圆形橙色腮红，换成了看得见毛孔的皮肤和自然的红润。由 Beatra AI 生成。*

提示词：

```text
[before] Close-up head-and-shoulders portrait of a fictional woman in her early thirties with shoulder-length wavy chestnut hair, hazel eyes and a soft closed-mouth smile, wearing a cream knit turtleneck sweater, standing in front of a softly blurred indoor cafe background with warm bokeh lights. Render it in the stereotypical glossy AI-generated portrait look: waxy, airbrushed, plastic-smooth skin with no pores, over-saturated orange-pink glow on the cheeks, a dreamy bloom haze, overly bright rim light, unnaturally perfect mirror-symmetric facial features and glassy doll-like eyes. Front-facing, centered, looking into the camera, both eyes clearly visible, hands out of frame, no text, no logos. ||| [after] Reduce the plastic, airbrushed AI look across this portrait so it reads like a real camera photograph. Restore natural skin texture with fine visible pores, subtle fine lines and slight natural unevenness in skin tone; replace the two round orange blush patches with a faint natural flush; tone down the over-saturated orange-pink glow, bloom haze and over-bright rim light to realistic warm cafe lighting with natural color; make the catchlights in the eyes small and natural. Preserve the same woman's identity and facial features, expression and closed-mouth smile, eye color, wavy chestnut hairstyle, cream knit turtleneck sweater, pose, framing, crop, cafe background and lighting direction. Do not add makeup, text or logos.
```

## 你能得到什么

- **先诊断，再动图** — 从解剖、材质、光影、背景、构图、文字和发布尺寸中，找出最影响真实感的一组问题。
- **能局部修，就不整张重来** — 局部缺陷做定点修复，全图质感和光影问题做整体精修，避免破坏接近成稿的画面。
- **保护已经满意的部分** — 尽量保留人物特征、商品外形、品牌细节、原有构图和无关区域。

## 适用场景

- **AI人像去塑料感** — 改善皮肤、头发、手指和面部细节，尽量保留人物已经确认的长相与神态。
- **商品图与电商图精修** — 修整反光、材质、阴影和重复背景，尽量保留商品外形、颜色、包装与品牌标识。
- **营销图与广告素材润色** — 处理违和细节和不统一光影，尽量保留所选信息层级、版式和主视觉。
- **小红书与社交封面去AI感** — 降低模板化和生成感，尽量保留裁切、安全区、主体和文字布局。

## 常见问题

### 可以修哪些常见的AI图片问题？

主要修复塑料感、手指和面部异常、重复纹理、光影不统一与模板化背景，并尽量保留已经满意的细节。

### 如何选择局部修复、全图精修或重新构图？

会按可见问题选择处理方式：明确破绽用局部修复，质感或光影问题用全图精修，需要更大幅度创意变化时再重新构图。

### 能保留人物长相和商品品牌吗？

会把人物特征、商品外形、颜色、包装与品牌标识列为必须保留的细节，并在完成后对照原图检查这些内容是否偏离。

### 精修后会怎样检查文字、Logo、手指和面部？

会针对明确问题修复并保持其余内容稳定，再对照原图复查文字、标识几何、手指与面部结构、人物特征和目标区域。

## 更新

安装后的 skill 每天最多检查一次新版本，替换前先校验官方归档，任何一步失败都不会动你已安装的版本。
随时可以关闭，见 skill 内的 `references/automatic-updates-and-safety.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。
