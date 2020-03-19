<font style="color: red;">この内容は2020/03改訂版です</font>
# 設計レビュー最終課題README
## やること
- 以下のレビュー対象の設計書について、レビューを行ってもらいます。
- **修了試験は2段階に分かれています。**
  - 1段階は**問題抽出**。
    - 対象の設計書について、添付している**markdownファイル**に、問題点を列挙してください。
    - 形式は、テンプレートの形を守ってください。
   - 2段階は**レビュー文章化**。
      - **問題抽出に合格してから取り組んでください。**
      - 1段階で提出した問題点について、要件に従う形にしてもらえるようレビュー文章を作成してください。
      - 形式は課題に対して、引用する書き方にしてください。

### レビュー形式例
```
## エンドユーザ
- 論理削除を考慮していない。（問題点）
  > ユーザを削除した場合、該当のレコードはどうなりますか？（レビュー）
```

## 準備(リポジトリのfork)
- このリポジトリをforkし、自分のアカウントで使うリポジトリを作成してください。

## 提出方法
- 設計図に対する問題点/レビューを該当するmarkdownファイルに記載してください。
- 問題抽出では、**１つの設計書を問題抽出するごと**に提出してください。
- レビュー文章化では、**全ての設計書をまとめて**提出してください。
- branchは**master**で行ってください。
- commit messageは`問題抽出_xxx_n回目`, `レビュー_n回目`としてください。
    - xxxは設計書の種類。
- 提出するときはfork先のリポジトリURLを[フォーム](https://forms.gle/DXSfWbYKxQH3hegG9)から提出してください。

## 研修担当からのレビュー
- 提出してもらったGithubリポジトリに対して、Pull Requestとしてレビューが飛んできます。
- **合格するまで**は、そのレビューを踏まえて修正を行い、再度[フォーム](https://forms.gle/DXSfWbYKxQH3hegG9)から提出をお願いします。

## レビュー対象の設計書
### データベース設計
- ER図
  - 01 : [リンク](https://app.diagrams.net?lightbox=1&highlight=0000ff&layers=1&nav=1&title=01_ER%E5%9B%B3_original#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1LucKDJ8Q-IyTijo15Oa8QB3qpTFnzkJt%26export%3Ddownload)
  - 02 : [リンク](https://app.diagrams.net?lightbox=1&highlight=0000ff&layers=1&nav=1&title=02_ER%E5%9B%B3_original#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1Kej_yGSBMVbzozraNAoutF95MYchVi5D%26export%3Ddownload)
- テーブル定義書
  - 01 : [リンク](https://docs.google.com/spreadsheets/d/1DepNODFa3pguiQiRd9XWs87JT77yJDvLGV1u0_xbwqs/edit?usp=sharing)
  - 02 : [リンク](https://docs.google.com/spreadsheets/d/1CvwjRLEYASTM987y8KZXTR34p5e0d3NUwOblYj6G_Gc/edit?usp=sharing)
  
### アプリケーション詳細設計
- 設計書 : https://docs.google.com/spreadsheets/d/1Cjml9dOAoxFqWhRMcyJQgRrpEzMlYDuIK6iu31tiTbA/edit?usp=sharing
- 画面は、下記ワイヤーフレームを参照してください。
  - [WF_Admin](https://app.diagrams.net?lightbox=1&highlight=0000ff&layers=1&nav=1&title=WF_Admin#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1O13FsfKsEv3Uz6N7iZSGbmiA6XdSd8ez%26export%3Ddownload)
  - [WF_Customer](https://app.diagrams.net?lightbox=1&highlight=0000ff&layers=1&nav=1&title=WF_Customer#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1PzZI4RsvRVwpfq9Pg7kQi2x1oxJiJogD%26export%3Ddownload)

# 設計書必須要件
以下は、必須要件になります。少なくとも以下の要件が満たされていることを確認しましょう。

## データベース設計要件
### 管理者
- メールアドレスとパスワードだけもつ

### ユーザ
- 登録時のデータは次の通り
	- 実名
	- 現住所(郵便番号含む)
	- 電話番号
	- メールアドレス
	- パスワード
- 現住所とは別に複数の配送先データをもつ
- 退会状態を管理する

### 配送先
- 宛名
- 郵便番号
- 住所

### 商品
- 商品名
- 税抜価格
- 発売日
- ジャケット画像(一つだけ)
- ディスク枚数
- ディスクに対応して曲を管理できる
- 販売ステータス
	- 販売中, 販売中止
- 商品ごとに、アーティスト・レーベル・ジャンルを一つずつ設定できる。

### 商品在庫関係
- 在庫数は入荷記録と受注詳細記録から算出する
- 入荷は、どの商品をいくつ入荷するか記録する。
- 受注詳細は、どの商品がいくつ、いくらで購入したか記録する

### 購入
- 複数の商品を指定した数で購入するためのカートデータをもつ
- 購入記録は次のデータを持つ
	- 購入者
	- 購入商品
	- 購入価格
	- 配送先
	- 送料
	- 配送ステータス
	- 購入方法(銀行振込、代引き、クレジットカード)
