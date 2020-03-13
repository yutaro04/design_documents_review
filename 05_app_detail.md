# アプリケーション詳細設計
## 全体
- 権限がuserとadminの両方にある場合urlを別々にしましょう。
- artists・labels・genresの記述がありません。
-ユーザ退会画面のアクションがありません。
-deviseがもともと生成するパスの記述がありません。

## users
- 論理的削除があるためdeleteを不要です。

## cds
- 論理的削除があるためdeleteを不要です。

## addresses
- 指摘事項

## cart_items
- editのワイヤフレームがありません。

## orders
- indexとnewのurlが同じです。

## order_details
- order_detailsにcreateは不要です。

## admins
- showとeditのurlが同じです。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
