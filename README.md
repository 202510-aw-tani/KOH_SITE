# KOH_SITE

KOH_SITE は、KOH の LP（ランディングページ）として利用する静的サイトです。  
本リポジトリは、予約処理そのものではなく、導線・文言整合・ページ表示を担当します。

## 役割
- LP としての情報表示（トップ / FAQ / 予約導線 / 完了案内）
- 予約導線の統一（`/reserve` へ遷移）
- サイト内で予約完了まで進む前提の文言整合

## KOH_APP との分担
- `KOH_SITE`: LP / FAQ / 導線 / 文言整合
- `KOH_APP`: 予約処理本体（送信受付、バリデーション、定員チェック、`/thanks` 遷移）

予約フォームは `action="/reserve"` / `th:action="@{/reserve}"` で APP 側受け口に接続する前提です。  
外部予約サイトへ遷移する構成ではありません。

## 対象ファイル
- `index.html`
- `faq.html`
- `reserve.html`
- `thanks.html`
- `styles.css`

## 確認方法
1. ブラウザで `index.html` を表示し、各予約導線が `/reserve` に向くことを確認
2. `reserve.html` のフォーム送信先が `/reserve`（POST）であることを確認
3. `faq.html` / `thanks.html` の文言が「サイト内で予約完了」方針と矛盾しないことを確認

APP の動作確認（送信・バリデーション・定員超過・`/thanks` 遷移）は `KOH_APP` 側で実施します。
