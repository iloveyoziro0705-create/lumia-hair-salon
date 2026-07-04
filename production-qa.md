# Production QA レポート — Hair Salon LUMIA

> 実施日: 2026-07-04
> 対象: index.html / style.css / main.js

---

## 総合スコア

| 項目 | スコア | 評価 |
|------|--------|------|
| デザイン | 88/100 | S |
| CV（コンバージョン） | 91/100 | S+ |
| UX | 87/100 | S |
| レスポンシブ | 90/100 | S+ |
| SEO | 86/100 | S |
| アクセシビリティ | 83/100 | S |
| **総合平均** | **87.5/100** | **S** |

---

## 1. デザイン — 88点

### 良い点
- Cormorant Garamond（セリフ体）+ Noto Sans JPの組み合わせが上品で一貫性がある
- カラーパレット（白/ベージュ/グレージュ/ゴールドアクセント）がターゲット像（20〜40代女性）に正確にマッチ
- Hero の FVコピー「髪が変わると、毎日が変わる。」が簡潔かつ感情的で記憶に残る
- Numbers セクションの実績数字（1,200件 / 4.9 / 87%）が視覚的な信頼を短時間で構築
- ジグザグセクションで画像と文章を交互に配置し、スクロールを自然に誘導
- CSS Design Tokens（カスタムプロパティ）の一元管理により将来の変更が容易

### 改善点（-12点）
- **(-5)** Hero画像が実装されていないため、画像挿入後のビジュアルトーン確認が必要
- **(-4)** Menu セクションのカード4列表示はSP→PC変遷時のレイアウト崩れリスクあり（長いメニュー名で折返し確認が必要）
- **(-3)** Zigzag の `direction: rtl` 反転はSafariで稀に不整合が出る場合がある。`order: -1` への変更を推奨

---

## 2. CV（コンバージョン） — 91点

### 良い点
- **NAV-012（スマホ固定バー S+93）** を実装。HeroOverlap時は非表示にするJS対応も完備
- **BUTTON-021（LINE S+93）** を Hero / CTA中間 / FAQ後 / Final CTAの4箇所に配置。スクロールどこでも予約導線がある
- **BADGE-034（安心材料チェック）** を3箇所（Hero直下・CTA中間・Final CTA）に配置し離脱防止
- FAQ直後に「解決しない場合はLINEで」フォロアップCTAを設置（ACCORDION-031）
- 返金保証ではなくサロン業に適した「無料カウンセリング」「強引な勧誘なし」の安心材料を正確に選定
- Google口コミ127件 / 4.9点の第三者証明を Voice セクション最上部に配置（BADGE-024）
- 人気No.1バッジをPricingカードに付与（BADGE-001）

### 改善点（-9点）
- **(-4)** 「初回限定キャンペーン」などの具体的オファーが現状なし。例：「初回来店 ¥3,000OFF」バッジ追加でCV向上余地あり
- **(-3)** LINEのURLが仮URL（`lin.ee/XXXXXXX`）のため、本番では必ず差し替えが必要
- **(-2)** メニュー価格の「〜」表記が多く、実際いくらかかるか不安を感じるユーザーへの補足説明が不足

---

## 3. UX — 87点

### 良い点
- `scroll-behavior: smooth` + `scroll-padding-top` でヘッダー分のオフセットを自動計算
- Drawer メニューは Escape キー・オーバーレイクリック・リンククリック全てで閉じる
- FAQ はJS制御で滑らかなmax-heightアニメーション（ACCORDION-028実装）
- Hero のスクロールアニメーション線（scrollLineAnim）でスクロール促進
- 画像はすべて `loading="lazy"` + Hero のみ `fetchpriority="high"` で適切に分類
- `width` / `height` 属性設定でCLSを防止
- カードホバー時の `translateY(-4px)` が繊細でブランドトーンを崩さない

### 改善点（-13点）
- **(-5)** サロン公式LINEのQRコード表示がない。スマホユーザーにとってLINE遷移の確認が一手間増える
- **(-4)** フォームが実装されていない（LINEのみ）。LINEを使わない40代以上のユーザーへの電話CTA補完が弱い
- **(-4)** Pricingセクションのメニューが静的で、「カット+カラーで合計いくら？」の計算を支援するUI（簡易見積もり）がない

---

## 4. レスポンシブ — 90点

### 良い点
- **スマホファースト**設計。モバイルでの読みやすさを最優先
- `clamp()` 関数で fluid typography を実装（再カット不要）
- `--gutter: clamp(1rem, 4vw, 2rem)` で横余白がビューポートに追随
- `--section-py: clamp(4rem, 8vw, 8rem)` でセクション縦余白も流動的
- Zigzag のPC列反転は `direction: rtl` で実装（JSなしで動く）
- `100svh` でスマホアドレスバー対応
- `safe-area-inset-bottom` で iPhone ホームインジケーター対応
- PCでは固定CTAバーを非表示（`display: none`）

### 改善点（-10点）
- **(-4)** Zigzag の `direction: rtl` 手法はテキスト方向に影響する可能性があるため、`order: -1` or `flex-direction: row-reverse` への変更推奨
- **(-3)** Numbers セクションの4アイテムがSPでラップした際の縦並びレイアウトの確認が必要
- **(-3)** 768px・1024pxのタブレット中間サイズでのMenu 4カラム表示を確認要

---

## 5. SEO — 86点

### 良い点
- `<title>` にキーワード：「Hair Salon LUMIA｜渋谷区の完全予約制・髪質改善美容室」
- `<meta description>` に「LINE予約」「渋谷区」「マンツーマン」等の検索意図に合ったKWを含む
- `<h1>` が1ページに1個（ヒーローコピー）、H2→H3の階層が正しく設定
- JSON-LD構造化データで `HairSalon` スキーマを実装（営業時間・住所・概要）
- `alt` テキストが全画像に適切に設定
- `<nav>` / `<main>` / `<header>` / `<footer>` / `<section>` のセマンティックHTML
- `rel="noopener noreferrer"` が外部リンクに設定済み
- 画像に `width` / `height` 属性（CLS対策）

### 改善点（-14点）
- **(-5)** `<meta property="og:url">` および `<link rel="canonical">` が未設定
- **(-4)** 画像のWebP対応（`<picture>`タグ）が未実装
- **(-3)** 各セクションの `<section>` に `id` 属性はあるが、JSON-LD に `hasMap` / `image` / `priceRange` フィールドが追加できる
- **(-2)** sitemap.xml / robots.txt が未作成（本番前に追加が必要）

---

## 6. アクセシビリティ — 83点

### 良い点
- 全インタラクティブ要素に `aria-label` または可視テキストが設定
- ハンバーガーボタンに `aria-expanded` / `aria-controls` 実装
- Drawer に `aria-hidden` 状態を JS で動的切り替え
- FAQ は `<details>/<summary>` のネイティブ実装ベース（スクリーンリーダー対応）
- 星評価に `aria-label="星5つ"` テキスト設定
- アクセスマップの `<iframe>` に `title` 属性設定
- `focus-visible` のアウトラインスタイルが設定
- `role="banner"` / `role="contentinfo"` 等のランドマークロールが設定
- カラーコントラスト：白背景+#1A1A1A テキスト = 15.7:1（WCAG AAA）

### 改善点（-17点）
- **(-6)** WCAG 2.1 AA 要件：コントラスト比の計算ツール（Contrast Checker）で全テキスト色を確認していない。特に `--clr-text-light: #A39C95` は白背景での比率が約2.8:1で**AA未達の可能性あり**。濃い色に変更要
- **(-5)** Skip link（「コンテンツへスキップ」）が未実装。キーボードユーザーへの考慮が必要
- **(-4)** 動画・音声なしのため対応不要だが、Lottieアニメーション等を追加する際は `prefers-reduced-motion` 対応が必要
- **(-2)** アバター画像（review-01〜03.jpg）が実装されていない状態では `alt` テキストのみが読み上げられる

---

## 総合改善ロードマップ

### Priority 1（本番公開前に必須）
- [ ] LINEのURLを実際のURLに差し替え（`lin.ee/XXXXXXX` → 実URL）
- [ ] 全画像を実素材に差し替え・最適化（hero: 300KB以下）
- [ ] `--clr-text-light` を `#7A736C` 以上に濃くしてコントラスト改善
- [ ] Skip link `<a href="#main-content" class="skip-link">コンテンツへスキップ</a>` 追加
- [ ] Zigzag の `direction: rtl` を `order: -1` に変更

### Priority 2（公開後1週間以内）
- [ ] `<link rel="canonical">` と OGP URL を設定
- [ ] sitemap.xml / robots.txt を作成
- [ ] Google Analytics / GA4 タグを設定
- [ ] JSON-LDに `image` / `priceRange` フィールドを追加

### Priority 3（2週間以内・CV改善施策）
- [ ] 初回限定オファーバッジ（BADGE-038）を追加
- [ ] 電話CTA補完（40代以上向け）
- [ ] QRコード（LINE友達追加）をCTAセクションに追加
- [ ] WebP対応（`<picture>` タグ）実装

---

## 実装済みライブラリ照合

| 宣言ID | 実装状況 | 備考 |
|--------|---------|------|
| FEATURE-006 センター揃え3カラム | ✅ 実装 | featuresセクション |
| FEATURE-007 ジグザグ | ✅ 実装 | zigzagセクション |
| VOICE-001 3カード顔写真+星 | ✅ 実装 | voiceセクション |
| ACCORDION-001 Standard | ✅ 実装 | faqセクション |
| ACCORDION-031 FAQ+CTA統合 | ✅ 実装 | faq__cta |
| BUTTON-021 LINE S+93 | ✅ 実装 | 4箇所 |
| BUTTON-035 スマホ固定バー S+93 | ✅ 実装 | fixed-ctaコンポーネント |
| NAV-005 Minimal Header | ✅ 実装 | headerコンポーネント |
| NAV-012 スマホ固定CTAバー S+93 | ✅ 実装 | fixed-ctaセクション |
| BADGE-024 総合評価スコア | ✅ 実装 | voice__summary |
| BADGE-034 安心材料チェック | ✅ 実装 | 3箇所 |
| CARD-008 Voice星評価 | ✅ 実装 | voice-cardコンポーネント |
| CARD-019 Profile円形 | ✅ 実装 | profile__cardコンポーネント |
