# AI Storyboard Video Studio

1枚の「3×3絵コンテ（16:9・9コマ）」から、キャラクターの見た目がぶれない9カットの動画を作るブラウザツールです。

**公開ページ:** https://hm-cmed.github.io/ai-storyboard-studio/

## 流れ

1. **STEP 1** 3×3絵コンテを OpenAI（gpt-image-1）で生成するか、ChatGPT等で作った画像を読み込む → 自動で9枚に分割
2. **STEP 2** Claude API が絵コンテを解析し、9カット分の動画プロンプト（英語）を自動記入
3. **STEP 3–4** fal.ai 経由で Seedance / Kling / Hailuo などの image-to-video モデルを呼び出し動画化（同時3本まで）

APIを使わず、画像の9分割とプロンプト管理だけに使うこともできます。

## APIキーの扱い

- キーは利用者自身のブラウザ（localStorage）にのみ保存され、このサイトのサーバーには送信されません。
- 各機能の実行時に OpenAI / Anthropic / fal.ai の各APIへ直接送信されます。
- 共用PCでは使用後に「キーを消去」してください。
- API利用料は各サービスのアカウントに課金されます。

## モデルIDについて

Claude のモデルIDと fal.ai のエンドポイントIDは入力欄で直接書き換えられます。提供終了などでエラーが出た場合は、各サービスの最新IDに変更してください。

## 構成

`index.html` 1ファイルのみ（Tailwind CDN を使用）。GitHub Pages（main ブランチ / ルート）で公開しています。

## License

MIT
