# work-project-master.html 変更ログ

## チーム構成と役割

- 基盤統合チームに「サポートデザイナー 1名」を追加
- 全メンバーに人数を追記（PdM 1名、エンジニアリーダー 🇻🇳 1名、エンジニア 🇻🇳 3名、QA 🇻🇳 2名）
- 「基盤統合チーム」「統合対象のプロダクトチーム」ラベルをカード外（上部）に移動
- 「統合対象のプロダクトチーム」の各チームを個別カードに変更
- 各プロダクトチームに「エンジニア」を追加
- ベトナム支社メンバー（エンジニアリーダー・エンジニア・QA）を「🇻🇳 ベトナム支社」ラベル付きグループにまとめる
- 「基盤統合チーム」「統合対象のプロダクトチーム」ラベルをプライマリーカラー（`var(--color-primary)`）に変更

---

## 問題セクション

- 画像プレースホルダーを削除
- 「併用ユーザーのプロジェクト運用不可が増大」「エンタープライズ企業の失注の要因に」を横並び（`grid-template-columns: 1fr 1fr`）に変更
- カードなしのシンプルなテキスト表示に変更

---

## ぶつかった課題と解決策

- 課題1タイトル：「ガイドライン・制約との両立」→「複雑な条件下でのUI作成」
- 課題2タイトル：「5プロダクト横断の合意形成コスト」→「4チーム間の課題感のズレによる議論の空中戦」
- 課題2説明文：「お互いに基盤化の重要性は理解していても、チームや立場によって優先したい観点が違っていた。その結果、議論が空中戦になりがちだったため、チーム間の課題の目線を揃えて「同じゴール」を見る仕組みが必要だった。」に変更
- 解決策2のタイトル：「ガイドラインとの合意形成」→「社内デザインガイドラインと実態を考慮し、UIを提案」

---

## デザインプロセス1・取り組み1

- STEPバッジ（STEP 01・STEP 02）を削除
- 「議論を即時可視化」の画像プレースホルダーを削除
- レイアウトを左右2カラムに変更（`grid-template-columns: 2fr 40px 1fr`）
  - 左：縦2段カード（議論を即時可視化 ＋ 非同期での深掘り）をグループコンテナで囲む
  - 中央：矢印カラム（40px）
  - 右：結果エリア
- カード間の矢印を `↓` `↑` 横並びの双方向矢印に変更
- 中央矢印を `→` のみに変更（左から右への流れ）
- 768px以下で縦並びになるレスポンシブ対応（`process1-layout` クラス追加）
- 「デザインの決定と並行して/機能要件が確定。」で改行
- 結果エリアのデザイン変更：
  - `background: #EEEDFE`・`border-radius: 12px`・`padding: 32px`
  - 「結果」ラベル追加（`color: #9896D8`）
  - 本文：`font-size: 15px`・`font-weight: 400`・`color: #6360B0`

---

## デザインプロセス2・取り組み1

- ステップ①：画像プレースホルダー削除、`grid-template-columns: 28px 1fr`
- ステップ②：画像維持、`grid-template-columns: 28px 1fr 360px`（240px → 360px に拡大）
- ステップ③：画像プレースホルダー削除、`grid-template-columns: 28px 1fr`

---

## デザインプロセス2・取り組み2

- 2x2グリッドの各キャプションテキストに `width: 100%; max-width: 100%; box-sizing: border-box;` を追加
- ①の画像を `<img src="images/work-pjm-process2-2-1.gif">` に変更（GIFアニメーション対応）

---

## デザインプロセス3

- 画像プレースホルダーを2枚縦並び（`flex-direction: column; gap: 12px`）に変更
  - `images/work-pjm-process3-1.png`
  - `images/work-pjm-process3-2.png`
- 画像を `aspect-ratio` なしの自然サイズ表示に変更（`max-width: 100%; height: auto;`）

---

## メインビジュアル

- ラッパーdiv・`aspect-ratio: 16/9` を削除
- `max-width: 100%; height: auto;` で画像本来のサイズで表示

---

## 全画像共通（3ファイル）

対象：`work-project-master.html`・`work-client-master.html`・`work-timecard.html`

- `object-fit: cover` → `object-fit: contain` に変更
- `background: var(--color-background-secondary)` を追加（余白をグレーで埋める）

---

## index.html — Worksカード画像

- Card 1（`thumb-pjm.png`）：`object-fit: cover` → `object-fit: contain` に変更後、`object-fit: cover` に戻す
- Card 2（`thumb-client.png`）・Card 3（`thumb-timecard.png`）：`object-fit: contain` → `object-fit: cover` に統一
- 結果：全3枚のWorksカード画像を `object-fit: cover` で176pxの枠をフルに埋める表示に統一
