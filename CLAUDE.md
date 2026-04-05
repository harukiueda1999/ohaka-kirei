日本語で応答してください。

# お墓きれい プロジェクト

## 概要
「お墓きれい」は、東京・神奈川を中心とした墓石清掃代行サービスのWebサイト。
Astro + Vercel で構築し、SEO記事・霊園別LPを量産する体制を整える。

**Astroプロジェクトは `/Users/uedaharuki/CLAUDE/ohaka-kirei/` に移動済み。**
作業時はそちらのディレクトリで行うこと。

## リポジトリ・URL
- GitHub: https://github.com/harukiueda1999/ohaka-kirei
- 本番: https://ohaka-kirei.jp
- Vercel: https://ohaka-kirei.vercel.app
- GitHubユーザー名: harukiueda1999

## 技術スタック
- フレームワーク：Astro
- ホスティング：Vercel（GitHub連携で自動デプロイ）
- フォーム：Googleフォーム（iframe埋め込み）
- 画像：public/images/ に格納

## ディレクトリ構成
```
src/
  layouts/
    Base.astro          # 共通レイアウト（ヘッダー・フッター・CSS変数）
    Article.astro       # SEO記事用レイアウト
    AreaLP.astro        # 霊園別LP用レイアウト
  components/
    Header.astro        # 共通ヘッダー（ロゴ：お墓きれい、CTA）
    Footer.astro        # 共通フッター（© 2026 お墓きれい）
    CTA.astro           # 共通CTAボタン（Googleフォームへのリンク）
  pages/
    index.astro         # トップLP
    area/               # 霊園別LP（20ページ）
      tama-reien.astro
      aoyama-reien.astro
      ...
    articles/
      [slug].astro      # 記事の動的ルーティング
  content/
    articles/           # SEO記事（Markdownファイル、40記事）
public/
  images/               # 画像ファイル
```

## デザインルール
- カラー：紺（#1a2c45）× 茶（#8b6f4e）× ベージュ背景（#f9f8f6）
- 見出しフォント：明朝体（Hiragino Mincho ProN）
- 本文フォント：ゴシック体（Hiragino Kaku Gothic ProN）
- トーン：落ち着き・信頼・丁寧。カジュアルすぎない
- 絵文字は使わない。番号（01, 02...）やCSSアイコンを使う

## Googleフォーム
```html
<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSflsamMLHBd9LgnTjPm5xKBRXpOF44xpDsxHeEXF87jdV5tRg/viewform?embedded=true" width="100%" height="1434" frameborder="0" marginheight="0" marginwidth="0"></iframe>
```

## SEO記事の作成ルール

### frontmatter形式
```markdown
---
title: "記事タイトル"
description: "meta descriptionに使う1文（120文字以内）"
date: YYYY-MM-DD
category: "お手入れ" | "料金" | "お墓管理" | "季節行事"
slug: "url-slug"
---
```

### 記事構成（この順番で必ず書く）
1. 読者の悩みを言語化する導入
2. 原因や背景を説明
3. 自分でできる対処法を紹介
4. 限界や注意点を示す（自力では難しいケース）
5. 業者依頼が向くケースを整理
6. サービスへの自然な導線（CTAコンポーネントを挿入）

### 文章のトーン
- 誇大表現は避ける
- DIYだけで終わらせない（業者依頼の選択肢も示す）
- スマホで読みやすい短い段落にする
- 「お墓きれい」のサービス紹介は記事末尾のCTAのみ。本文中で宣伝しない

## 霊園別LP作成ルール

### 共通（トップLPと同じ）
- サービス概要、清掃内容、写真報告、料金、流れ、CTA

### 霊園ごとに変える部分
- H1に霊園名を含める
- meta title / description に霊園名を含める
- 地域文脈の説明文（アクセス感・距離感）
- よくある依頼背景（その霊園特有の事情）
- FAQの一部

### 霊園LP作成の優先順位
1. 多磨霊園
2. 青山霊園
3. 小平霊園
4. 谷中霊園
5. 以降は問い合わせが来た霊園から

## デプロイ
- `git push origin main` → Vercelが自動デプロイ
- 記事追加もpushするだけで公開される

## 事業戦略の参照先
詳細な事業戦略・判断は以下のファイルを参照：
- `/Users/uedaharuki/CLAUDE/My Obsidian/business-strategy.md`
- `/Users/uedaharuki/CLAUDE/My Obsidian/site-build-steps.md`
