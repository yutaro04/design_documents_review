# テーブル定義書1
## 全体
- テーブル名の命名は小文字から始まり、複数系にする必要があります。例）users
  > 命名規則にしたがって命名しましょう

- 単語の間に空白がある場合はスネークケースも必要になります 例)cart_items
  > 「_」で文字をつなげることを、スネークケースといいます

- 全テーブルのPKにおいて、AUTO_INCREMENT、INDEXにはデフォルトで◯が入っています

- 各テーブルに必ず１つ必要なPKに◯が一つも入って無い箇所があります
  > PKは１テーブルに１つ必要です

- 各テーブルのPKになるカラム名は適切でしょうか
  > カラム名を「カラムの入っているテーブル名_id」のように、カラム名の先頭にテーブル名を付けていますが、あまり好ましくありません。例）Adminテーブルでの「admin_id」

- 各テーブルにおけるcreated_at,updated_atのカラム説明は適切な命名ですか？
  > テーブルによって呼び方が変わりませんか？

- 入荷用の情報を管理できることが好ましいです
  > 入荷を管理しないと、商品の管理が難しくなります

## Users
- 郵便番号、電話番号のデータ型は適切ではありません
  > integer型では、先頭に0を入力しても記録されません。例）入力：090-xxx-xxxx -> 結果：90-xxx-xxxx

- 名前（名、名カナ）のNOT NULLに◯がありません
  > 今のままでは、空白で保存ができます。

- l_name,f_nameのように文字を省略する命名は正しいですか？
  > 省略しての命名は好ましくありません

- member_statusのカラム名の命名は適切ですか？
  > 説明の日本語とカラム名の英語が異なっています。

- 退会ステータスのデータは「退会しているor退会していない」の二択です。現在のデータ型は適切でしょうか。
  > string型は文字列を記録します。trueかfalseを判断するデータ型が存在します。

- 現在の設計において、配送先を複数登録することは可能でしょうか
  > 複数の連絡先を登録できるようにしましょう

## Products
- PKの命名は適切ですか？
  > カラムの命名は単数系が適切です

- 本来FKに◯が必要なところに◯が入っていません
  > 外部キーがどれかを見直して見ましょう

- 「notax」は２語です、カラムの命名規則に沿って「no_tax」にしましょう
  > 文字と文字の間に「_」を入れることを「スネークケースといいます」

- ジャケット画像のデータ型が適切ではありません
  > 画像を入れるためのデータ型は何を使用していましたか？

- cd_imageがrefileを使っている場合、_idの追記が必要になります

- stock_statusは在庫数から判断できるため不要です
  > 他のカラムなどから判断できるため、不要なカラムになります。

- stockは（入荷数-購入数）から計算できるため不要です。
  > 他のカラムから計算でき、情報を保持する必要もないので、不要なカラムになります。

- Discsとの関係は適切ですか？
  > どちらが親要素になりますか？ ER図も見直してみましょう。

## Discs

- FKの命名は適切ですか？
  > カラム名の命名は単数系が適切です。

- 「track_num」の意味はこのテーブルで適切でしょうか
  > トラックNoは、ディスクの番号という意味でしたか？

## Songs
- 曲名のデータ型は正しいですか？
  > integer型は整数を扱います。

- 曲の順番はどのように管理しますか？
  > 曲の順番がわからなくなります。

- カラム名 「song」の命名は適していますか？
  > 「song」だけでは何を表しているかがわかりません。

## Labels
- productsとの関係性は適切ですか？
  > productsとの親子関係はどのようになっていますか？

- 商品idのカラム名は単数系が適切です

- labelsテーブルのidが存在しません。また、PKが存在しません。
  > PKは各テーブルにつき１つ必要です。

- カラム名 「label」の命名は適していますか？
  > labelでは何を表しているのかがわかりません。

## Artists
- productsテーブルとの関係性は適切ですか？
  > productsとの親子関係はどのようになっていますか？

- 商品idのカラム名は単数系が適切です

- artistカラムのデータ型は適切でしょうか？
  > integer型は整数を扱います。

- FKにAUTO INCREMENTは必要でしょうか？
  > AUTO INCREMENTをFKに付けた場合はどうなりますか？

- artistテーブルのidが存在しません。また、PKが存在しません。
  > PKは各テーブルにつき1つ必要です。

- カラム名 「artist」の命名は適していますか？
  > 「artist」だけでは何を表しているのかが不明です。

## Genre
- 商品idのカラム名は単数系が適切です

- productsテーブルとの関係性は適切ですか？
  > priductsとの親子関係はどうなっていますか？

- artistテーブルのidが存在しません。また、PKが存在しません。
  > PKは各テーブルにつき1つ必要です。

- FKにAUTo INCREMENTは必要でしょうか？
  > AUTO INCREMENTをFKに付けた場合はどうなりますか？

- ジャンル名のデータ型は適切でしょうか
  > integer型は整数を扱います。

- カラム名 「genre」の命名は適していますか？
  > genreだけでは何を表しているのかがわかりません

## Cart item
- 商品idのカラム名は単数系が適切です

- products_idにデータ型がありません
  > 適切なデータ型を入力しましょう

- 「小計金額」をデータとして保存することは適切ですか？
  > 他のカラムから計算できる場合は、データを保持する必要はありません。

- 「buy num」のように文字を省略する命名は適切ではありません

## Buy
- buyテーブルの命名は適していますか
  > 管理者目線での命名を心がけましょう。

- buy_detailsとの関係性は適切ですか？
  > どちらが親要素かを確認しましょう。また、ER図も確認してみましょう。

- 「pay,stock」の命名は適切ですか？
  > 「pay,stock」だけでは、何を表しているのかがわかりません。

- 購入者の住所、郵便番号を管理するカラムが存在しません
  > どこに送ったかを管理できるようにしましょう

- お支払い方法のデータ型が好ましくありません
  > string型だと、同じ文字列を何回も保存することになります。enumなどを使いましょう。

## Buy details

- テーブル名の命名は適していますか？
  > 単語と単語の間には空白を入れずに「_(アンダーバー)」を入れましょう

- 「buy num」のように文字を省略する命名は適切ではありません
  > また、こちらにもアンダーバーを入れましょう

- 購入時と現在の価格が常に同じでしょうか？
  > 購入後に価格が変更されると、購入時の価格がわからなくなります

- 商品idがありません
  > 商品の情報がないと何を購入したかがわからなくなります。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。


# 研修担当レビュー
<font color="Red">再提出の際はこのレビューを残しておいてください。</font>

## 全体
- 具体的に命名規則のどの部分に反しているのか明示してください。(前回)
> テーブル名の命名は小文字から始まり、複数系にする必要があります。例）users
  - と回答されていますが、"Cart item"のように空白が入っているのもNGです。
    - スネークケースも必要になります。→cart_items
- カラムの命名規則は正しいですか？(前回)
  - 追記: カラム名に接頭辞は不要です。
    - 例えばusersテーブルのuser_telカラムは、telで十分であり、"user_"という接頭辞は冗長で、カラム名が長くなるので避けた方が無難になります。
    - x @user.user_tel → o @user.tel
  - ですので、該当テーブルでこのことを指摘しましょう。

## user
- 現在の設計で、配送先を複数登録できますでしょうか。

## products
- discs項で
> Productsとの関係は適切ですか？
- とありますが、今は商品、ディスクが互いのFKを持っている状態になります。
  - ディスクに商品idは必要であり、逆に商品にディスクidが不要なので、この指摘はproductsでするべきです。

## discs
- track_noの用途は適切でしょうか。
  - 言葉自体の意味を今一度ご確認ください。

## songs
- song_nameと修正案として提示していますがそのカラムの命名は正しいですか？(前回)
  - 追記: 全体項で「カラム名に接頭辞は不要」と申し上げた通り、ここでは"song_"はつかうべきでなく、例えばnameが適切です。

## labels
- label_nameと修正案として提示していますがそのカラムの命名は正しいですか？(前回)
  - 追記: songs同様。

## artists
- artist_nameと修正案として提示していますがそのカラムの命名は正しいですか？(前回)
  - 追記: songs同様。

## genres
- genre_nameと修正案として提示していますがそのカラムの命名は正しいですか？(前回)
  - 追記: songs同様。
- ジャンル名のデータ型は適切でしょうか。

## buy
- buyテーブルの命名は適していますか？(前回)
  - 追記: buyは"購入"です。管理者視点になっていません。
- 購入者の郵便番号を管理するカラムがありません。(前回)
  - 追記:住所も抜けています。※指摘漏れ
- 支払い方法のデータ型が不適当です。
   - string型だと、例えば"銀行振込"→"振込"に変更したいなど、複数レコードを更新する際に非常に手間です。
     - 加えてstring型だと全角文字でデータサイズが大きくなり、DBに不可がかかるため、enumでintegerにするのが適当になります。

## buy_details 
- テーブルの命名は適していますか？(前回)
  - 追記: buy_detailsは"購入詳細"です。管理者視点になっていません。
- 商品テーブルとのリレーションがありませんが、購入履歴はどのように保存しますか。(前回)
  - 追記: ER図02で指摘しましたが商品idがないと色々と不都合なので、レビュー時に分かりやすく書いていただければと。
    - 問題指摘的には"商品idがない"でOKです。

# フィードバック
[add]→付け加えなければいけないところ
[fix]→修正が必要なところ
[comment]→その他コメント（修正ではないけど、確認して欲しいポイントです）

- 以下の点の修正をお願い致します。

- 細かい点となりますが、以下の修正をお願いします。

## artists,genres,labels
- それぞれの名称カラムは「name」の方がより良いです。「Artists/artist」よりも「Artist/name」のほうが何を意味しているのかわかりやすいため。

## フィードバック
- 合格です！！
