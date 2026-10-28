# AI Image Realism Skill

[English](./README.md) | [简体中文](./README.zh-CN.md) | 日本語

> 👉 こちらもどうぞ [AI Image Generator Skill](https://github.com/beatra-ai/ai-image-generator-skill)

既存の AI ポートレート、商品画像、販促ビジュアルの不自然な肌、崩れた手や顔、繰り返し模様、一貫しないライティングを直して自然に。Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw のどれからでもそのまま使えます。

> [!IMPORTANT]
> 生成には [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-image-realism-skill) アカウントが必要で、クレジットを消費します。スキル自体のインストールは無料です。

| 項目 | 内容 |
| --- | --- |
| **できること** | AI生成画像の不自然な肌、手指・顔の崩れ、反復模様、光と影の矛盾を補正し、人物・商品・販促画像を自然に仕上げます。 |
| **モデル** | Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live |
| **動作要件** | Python 3.10 以上と、`SKILL.md` を読み込めるエージェント |
| **費用** | インストールは無料。生成のたびに Beatra アカウントのクレジットを消費しますが、課金されるのは、その生成を明示的に依頼したとき、または確認カードを承認したときだけです。 |
| **対応エージェント** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="このデモのためにわざと蝋のような肌と過剰な彩度の AI っぽい見た目で生成した架空の女性のポートレートを、顔、ポーズ、セーター、カフェの背景を保ったまま、自然な肌の質感と温かみのある現実的な光に修復。Beatra AI で生成。"></p>

*このデモのためにわざと蝋のような肌と過剰な彩度の AI っぽい見た目で生成した架空の女性のポートレートを、顔、ポーズ、セーター、カフェの背景を保ったまま、自然な肌の質感と温かみのある現実的な光に修復。Beatra AI で生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-image-realism`](skills/ai-image-realism) | [SKILL.md](skills/ai-image-realism/SKILL.md) | 0.3.7 |

このリポジトリは [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-image-realism) から自動的に公開されています。問題の報告はそちらへお願いします。

## インストール

[`skills`](https://skills.sh) CLI を使う場合：

```bash
npx skills add beatra-ai/ai-image-realism-skill
```

Claude Code プラグインとして：

```bash
claude plugin marketplace add beatra-ai/ai-image-realism-skill
claude plugin install ai-image-realism@ai-image-realism-skill
```

Codex プラグインとして：

```bash
codex plugin marketplace add beatra-ai/ai-image-realism-skill
codex plugin add ai-image-realism@ai-image-realism-skill
```

GitHub Copilot CLI プラグインとして：

```bash
copilot plugin marketplace add beatra-ai/ai-image-realism-skill
copilot plugin install ai-image-realism@ai-image-realism-skill
```

Gemini CLI 拡張機能として：

```bash
gemini extensions install https://github.com/beatra-ai/ai-image-realism-skill
```

GitHub CLI を使う場合：

```bash
gh skill install beatra-ai/ai-image-realism-skill ai-image-realism
```

または、このリポジトリをクローンして `skills/ai-image-realism` を次の場所にコピーします：Claude Code は `~/.claude/skills/`、Cursor は `~/.cursor/skills/`、Codex は `~/.agents/skills/`、Windsurf は `~/.codeium/windsurf/skills/`、Cline は `~/.cline/skills/`、OpenClaw は `~/.openclaw/skills/`。

または、次の文をエージェントに貼り付けてください：

```text
https://github.com/beatra-ai/ai-image-realism-skill から ai-image-realism スキル（フォルダ skills/ai-image-realism）をインストールし、その SKILL.md に従って私の Beatra アカウントに接続してください。
```

## 作例

<p align="center"><img src="assets/demo-2.webp" width="800" alt="同じ顔の修復前後のクローズアップ。エアブラシのような肌と丸いオレンジ色のチークが、見える毛穴と自然な血色に置き換わっている。Beatra AI で生成。"></p>

*同じ顔の修復前後のクローズアップ。エアブラシのような肌と丸いオレンジ色のチークが、見える毛穴と自然な血色に置き換わっている。Beatra AI で生成。*

エージェントへの依頼例：

```text
./portrait-waxy.png の AI っぽさを直して：肌に毛穴の見える本物の質感を与え、丸いオレンジ色のチークを自然な血色に置き換え、光を温かくして。顔、ポーズ、セーター、カフェの背景は変えないで。
```

プロンプト：

```text
[before] Close-up head-and-shoulders portrait of a fictional woman in her early thirties with shoulder-length wavy chestnut hair, hazel eyes and a soft closed-mouth smile, wearing a cream knit turtleneck sweater, standing in front of a softly blurred indoor cafe background with warm bokeh lights. Render it in the stereotypical glossy AI-generated portrait look: waxy, airbrushed, plastic-smooth skin with no pores, over-saturated orange-pink glow on the cheeks, a dreamy bloom haze, overly bright rim light, unnaturally perfect mirror-symmetric facial features and glassy doll-like eyes. Front-facing, centered, looking into the camera, both eyes clearly visible, hands out of frame, no text, no logos. ||| [after] Reduce the plastic, airbrushed AI look across this portrait so it reads like a real camera photograph. Restore natural skin texture with fine visible pores, subtle fine lines and slight natural unevenness in skin tone; replace the two round orange blush patches with a faint natural flush; tone down the over-saturated orange-pink glow, bloom haze and over-bright rim light to realistic warm cafe lighting with natural color; make the catchlights in the eyes small and natural. Preserve the same woman's identity and facial features, expression and closed-mouth smile, eye color, wavy chestnut hairstyle, cream knit turtleneck sweater, pose, framing, crop, cafe background and lighting direction. Do not add makeup, text or logos.
```

## 技術仕様と出力上限

2026-10-18 時点。最新の一覧：https://docs.beatra.ai/ja/docs/models

- **アップロード** — 1 ファイルあたり最大 100 MB。下記の各モデルの入力制限も適用されます
- **画像編集** — 6 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 4.2 MP
  - 4.2 MP（2K ティア）：Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro（1 リクエストあたり最大 4 枚）
  - 入力画像：1 リクエストあたり最大 4 枚、各 10〜20 MB／BMP、GIF、JPEG、PNG、TIFF、WEBP
- **画像から画像** — 10 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 16.8 MP
  - 16.8 MP（4K ティア）：GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（1 リクエストにつき 1 枚）
  - 入力画像：1 リクエストあたり最大 4 枚、各 10〜20 MB／BMP、GIF、JPEG、PNG、TIFF、WEBP

## 得られるもの

- **変更する前に診断** — 人体、質感、光、背景、構図、文字、掲載先との適合を確認し、最も影響の大きい問題に絞ります。
- **必要な範囲だけを補正** — 局所的な欠陥は限定して直し、画像全体の質感や光だけが問題なら全体を整えます。
- **良い部分を守る** — 人物の特徴、商品の形、ブランド要素、構図、問題のない領域をできるだけ保ちます。

## 活用シーン

- **AIポートレートを自然に** — 肌、髪、手指、顔の細部を整え、人物の特徴や表情をできるだけ保ちます。
- **商品・EC画像をレタッチ** — 反射、素材感、影、背景の反復を直し、商品の形、色、包装、ブランド表示をできるだけ保ちます。
- **販促・広告ビジュアルを調整** — 気になる破綻や光の不整合を直し、選んだメッセージ、レイアウト、主役をできるだけ保ちます。
- **SNSカバーのAI感を軽減** — 定型的な見た目を抑え、トリミング、安全領域、被写体、文字配置をできるだけ保ちます。

## よくある質問

### どのようなAI画像の問題を補正できますか？

不自然な肌、崩れた手指や顔、反復模様、光の不整合、定型的な背景を中心に直し、良い部分をできるだけ保ちます。

### 部分補正、全体レタッチ、再構成はどう選びますか？

見える問題に合わせて選びます。特定の破綻は部分補正、質感や光は全体レタッチ、より大きな表現変更を望む場合は再構成を使います。

### 人物の特徴や商品のブランド要素を保てますか？

人物の特徴、商品の形、色、包装、ブランド表示を残す要素として整理し、完成後に元画像と比較してずれを確認します。

### レタッチ後の文字、ロゴ、手指、顔はどう確認しますか？

指定した問題を直しながら他の内容を保ち、文字、ロゴ形状、手指と顔の構造、人物の特徴、補正箇所を元画像と見比べます。

## 更新とセキュリティ

2026 年 10 月のリリース以降、このスキルに自動更新機能はありません。インストールしたファイルだけを実行し、
自動的に置き換えることはありません。更新はインストールに使ったツール（`npx skills update ai-image-realism` または
`gh skill update ai-image-realism`）で行ってください。詳細はスキル内の `references/updates-and-security.md` を参照してください。

## ライセンス

[MIT-0](LICENSE)：商用を含め、自由に使用・改変・再配布できます。クレジット表記は不要です。ClawHub 上のこれらのスキルと同じ条件です。

## リンク

- ウェブサイト — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-image-realism-skill
- ドキュメント — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-image-realism-skill
- コンソール — https://console.beatra.ai
- AI エージェント向け — https://beatra.ai/llms.txt （インデックス）· https://beatra.ai/llms-full.txt （全スキルを 1 ファイルに）
