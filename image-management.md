# 画像管理リスト — Hair Salon LUMIA

> 最終更新: 2026-07-04

---

## 画像ファイル一覧

| No. | ファイルパス | 用途 | 推奨サイズ | 推奨構図 |
|-----|------------|------|------------|---------|
| 01 | assets/images/hero-main.jpg | Heroセクション メインビジュアル | 1920×1080px | 縦構図または横構図 / 自然光が差し込む半個室サロン全体または施術中の女性後ろ姿 |
| 02 | assets/images/concept-salon.jpg | Conceptセクション サロン内観 | 800×1000px | 縦構図 / 白とベージュの内装・チェア・鏡 |
| 03 | assets/images/treatment-color.jpg | Zigzagセクション カラー施術 | 800×940px | 縦構図 / スタイリストの手元でカラー剤を塗布するアップ |
| 04 | assets/images/treatment-hair.jpg | Zigzagセクション 髪質改善 | 800×940px | 縦構図 / 艶やかな髪のクローズアップ（横から光が当たる） |
| 05 | assets/images/stylist-profile.jpg | Stylistセクション スタイリスト | 640×750px | 縦構図 / スタイリストの上半身ポートレート / 自然光・白背景または明るいサロン内 |
| 06 | assets/images/review-01.jpg | Voiceセクション お客様01 | 112×112px | 円形トリミング想定 / 女性の顔写真（正面） |
| 07 | assets/images/review-02.jpg | Voiceセクション お客様02 | 112×112px | 円形トリミング想定 / 女性の顔写真（正面） |
| 08 | assets/images/review-03.jpg | Voiceセクション お客様03 | 112×112px | 円形トリミング想定 / 女性の顔写真（正面） |
| 09 | assets/images/cta-bg.jpg | Final CTAセクション 背景 | 1920×800px | 横構図 / ヘアセット後の女性の後ろ姿 or サロン内・窓からの自然光 |
| 10 | assets/images/og-image.jpg | OGP画像 SNSシェア用 | 1200×630px | Heroと同じ or LUMIA ロゴ+サロン内観 |

---

## 画像フォルダ構成

```
assets/
└── images/
    ├── hero-main.jpg          ← 最重要・LCP対象
    ├── concept-salon.jpg
    ├── treatment-color.jpg
    ├── treatment-hair.jpg
    ├── stylist-profile.jpg
    ├── review-01.jpg
    ├── review-02.jpg
    ├── review-03.jpg
    ├── cta-bg.jpg
    └── og-image.jpg
```

---

## 各画像 詳細仕様

### 01. hero-main.jpg（最重要）
- **用途**: Heroセクション全画面背景
- **推奨サイズ**: 1920×1080px（2x: 3840×2160px）
- **ファイル形式**: JPEG / WebP推奨
- **推奨構図**: 自然光の差し込むサロン内・施術中の女性の後ろ姿または横顔。テキスト配置のため中央〜下部を人物に、上部は少し余白を持たせる。
- **配色イメージ**: 白・ベージュ・グレージュ系。暖かみのある柔らかい光。
- **検索ワード**: "hair salon interior natural light", "beauty salon private room", "hair stylist female client", "japanese hair salon aesthetic"
- **最適化**: fetchpriority="high" 設定済。必ずファイルサイズを最適化すること（目安: 300KB以下）

---

### 02. concept-salon.jpg
- **用途**: Conceptセクション サロン内装
- **推奨サイズ**: 600×750px
- **推奨構図**: サロンの内観全体。チェア・鏡・サイドテーブル。白を基調とした空間に木材や植物などの自然素材をアクセントに。縦長構図。
- **配色イメージ**: 白・アイボリー・ナチュラルウッド
- **検索ワード**: "minimalist hair salon interior", "private hair salon room white", "salon chair mirror aesthetic"

---

### 03. treatment-color.jpg
- **用途**: Zigzag ダメージレスカラーセクション
- **推奨サイズ**: 600×700px
- **推奨構図**: スタイリストの手元アップ。ハケでカラー剤を丁寧に塗布しているシーン。または施術中の女性（横顔・後ろ姿）。自然光。
- **検索ワード**: "hair color treatment close up", "hair dyeing process stylist hands", "hair coloring natural light"

---

### 04. treatment-hair.jpg
- **用途**: Zigzag 髪質改善セクション
- **推奨サイズ**: 600×700px
- **推奨構図**: 艶やかな黒髪または茶髪のクローズアップ。横から光が当たりツヤが伝わる。髪の毛が綺麗に流れているシーン。
- **検索ワード**: "shiny healthy hair close up", "hair gloss treatment result", "beautiful asian hair texture"

---

### 05. stylist-profile.jpg
- **用途**: Stylistセクション スタイリストのプロフィール写真
- **推奨サイズ**: 480×560px
- **推奨構図**: スタイリスト上半身。白背景または明るいサロン内。プロフェッショナルな印象だが柔らかい表情。目線はカメラに向けるか少し外す。縦構図。
- **検索ワード**: "female hair stylist portrait professional", "beauty professional headshot natural light", "japanese stylist portrait"

---

### 06-08. review-01〜03.jpg
- **用途**: お客様の声セクション 口コミ写真
- **推奨サイズ**: 112×112px（2x: 224×224px）→ 円形トリミング
- **推奨構図**: 女性顔写真（正面または斜め）。自然な笑顔。年代：01=30代、02=20代後半、03=40代。
- **検索ワード**: "japanese woman portrait smile", "customer review headshot"
- **注意**: 実際の顧客写真を使用する場合は必ず書面での許諾を取得すること

---

### 09. cta-bg.jpg
- **用途**: Final CTAセクション 背景画像（テキストオーバーレイあり）
- **推奨サイズ**: 1920×800px
- **推奨構図**: 施術後の女性の後ろ姿・横顔（鏡越し）。または窓からの自然光が差し込むサロン内。暗めのオーバーレイを乗せるため、やや明るめの写真でも可。
- **検索ワード**: "hair salon window light woman", "hair done reflection mirror salon", "beauty salon mood lighting"

---

### 10. og-image.jpg
- **用途**: SNSシェア・OGP
- **推奨サイズ**: 1200×630px
- **推奨構図**: LUMIAロゴ + サロン内観 or ヘアスタイルアフター写真。テキスト「Hair Salon LUMIA / 渋谷区」を入れること。
- **ツール**: Canva / Figma で制作推奨

---

## 画像最適化チェックリスト

- [ ] hero-main.jpg は 300KB以下に圧縮（Squoosh / TinyPNG）
- [ ] それ以外の画像は 150KB以下推奨
- [ ] WebP形式への変換を検討（`<picture>` タグで JPEG フォールバック）
- [ ] すべての `<img>` に `alt` テキストが設定されているか確認
- [ ] hero-main.jpg は `fetchpriority="high"` 設定済み
- [ ] その他の画像は `loading="lazy"` 設定済み
- [ ] `width` / `height` 属性が設定されているか確認（CLS対策）
