# "HTTP"にまつわる用語について

## URLとは？

**「Uniform Resource Locator」** の略で、簡単にいえばインターネット上のホームページ（Webサイト）やファイルの位置や情報を示すもの。

![http image](https://living-maou.com/wp-content/uploads/2024/01/internet-mechanism06.png)

## クエリ文字列とパスパラ変数

### クエリ文字列とは？

クエリ文字列とは、サーバーに情報を送るためにURLの末尾につけ足す文字列（変数）のこと。

「?」をURLの末尾につけ、その次に「パラメーター＝値」をつけ、複数のパラメーターをつけたい場合は「&」を使用する。この形式で、サーバーに送信したいデータをURLにつけ加えることが可能。

ex）

基本のURLが「https:// ○△×□.jp/」だとして、基本のURLにクエリ文字列（URLパラメーター）を加えると
「https:// ○△×□.jp/?●=▲×■&○=△×□」となる。
「?●=▲×■&○=△×□」の部分が、クエリ文字列（URLパラメーター）。

### パス変数とは？
#### パスとは？
使用するファイルなどがある位置を示す文字列。

パス変数とは、URLのパス部分に含まれる変数のこと。
一般的に、動的なWebページやAPIエンドポイントで使用され、URL内の特定の部分に値を指定するために使用される。

ex）

https://example.com/users/{username}

このURLでは、{username} がパス変数。これは、ユーザーの特定のユーザー名を示すために使用され、実際のリクエスト時には、{username}の部分に具体的なユーザー名が入る。 パス変数は、Webアプリケーションで特定のリソースを識別し、操作するための重要な仕組みである。

### クエリ文字列とパス変数の違いについて
〇クエリ文字列

特定のもの（画面など）に条件を加える場合に必要なるもの。
データベースに対する命令文、もしくは、検索キーワード！

〇パスパラメーター

特定のもの（画面など）を表示したいときに必要になるもの。

## Http とは？ 
<span style="color:red;">「Hyper Text Transfer Protocol」</span>の略。
ホームページのファイル等を受け渡しするときに使うお約束事。

### Httpメゾットとは？ 
対象となるリソースに対して、何をしたいのか指示をする。

メソッドは、HTTPプロトコルにおいてクライアントとサーバー間でデータの取得、作成、更新、削除などの操作を行うために使用される。
以下の5つが主なもの。

| プロトコル名                      | 説明                                       |
|----------------------------------|------------------------------------------|
| GET（参照）       | 指示の実行者の手元に使えるようにデータを取ってくる。欲しい情報の詳細を記述する。|
| POST（新規作成）  |副作用をともなうデータを送ることができる。新しくデータを作成するときによく使用する。新規作成したいデータの情報を追加で送信できる。|
| PUT（更新）                       |すでに存在しているデータを上書きして更新する。更新の対象や更新内容などの情報を追加で送信できる。|
| PATCH（一部更新）                  |PUTと同じ更新のリクエストだが、PUTと違い、一部更新するときに使う。更新の対象や更新内容などの情報を追加で送信できる。|
| DELETE（削除）               | すでに存在しているデータを削除する。削除の対象の情報を追加して記述する。|

### リクエストヘッダーとは？

取得するリソース（動作の実行に必要な処理システムの要素）又はクライアント自体に関する詳細情報を含むヘッダーのこと。

### HTTPリクエストとは？

ブラウザなどからURLを指定して、ネットワーク上のWEBサーバからファイルやWEBページなどを返すようにリクエスト(要求)すること
HTTPリクエストは、URL、HTTPメソッド（GET、POST、PUTなど）、リクエストボディ（必要な時のみ）、およびヘッダーから構成される。ヘッダーは、リクエストに関する補足的な情報を提供し、リクエストの処理やサーバーの応答に影響を与えることがある。

| リクエスト名                   | 説明                                                                                                                         |
|--------------------------|----------------------------------------------------------------------------------------------------------------------------|
| User-Agent               | インターネットを閲覧しているユーザーの、デバイス・OS・ブラウザなどの情報を文字列にしたもの。 Webサーバはクライアントがどのバージョンの何というOSで稼働しているか、マシンは何か、Webブラウザなのかアプリなのか、といったことを識別できる。 
| Accept language         　　　 |クライアントがどの言語（英語や日本語など）が理解できるのか、どのロケーションが推奨されているのかを識別するのに使う。|
| Authorization            |認証情報を含み、クライアントが保護されたリソースにアクセスする際に使用される。|
| Cookie                   |クライアントがサーバーに保存したクッキーを含み、セッションの管理や認証などの目的で使用される。|

*他にも沢山のHTTPリクエストがある。

### HTTPステータスコードとは？
HTTPレスポンスに含まれるWebサーバーの処理結果を表現する3桁の数字のことを指す。 3桁の数字は「処理が成功した」、「リダイレクト（転送）がかかっている」、「エラーがある」、等の様々な意味を持っている。

| HTTPステータスコード　　　　　　 | 説明                                                                                                  |
|--------------------|-----------------------------------------------------------------------------------------------------|
 | 200                |OK(成功)　|
| 201                |   Created(作成完了)|
 400                |  Bad Request (不正なリクエスト)|
 404                |  Not Found (リソースが見つからない)|
 500                | Internal Server Error (サーバー内部のエラー)|

### レスポンスヘッダーとは？
HTTP レスポンスで使用できる HTTP ヘッダーで、メッセージの内容には関連しないもの。 Age, Location, Server のようなレスポンスヘッダーは、レスポンスのものより詳細な文脈を提供するために使用される。

![http image](https://digiful.irep.co.jp/hs-fs/hubfs/76975541525_01.jpg?width=1600&name=76975541525_01.jpg)

| よく使われるもの　　　　　　 | 説明                                                                                                  |
|----------------|-----------------------------------------------------------------------------------------------------|
| Allow          |   受理可能なメゾット|
| Date           | 生成した日時|
| Etag　          |内容を要約する情報（この変化により更新内容がわかる）|
| Set Cookie     | 保存すべきCookieの内容|

＊他にも沢山ある。

### レスポンスボディとは？
HTTPレスポンスを構成するものの一部で、「相手が欲しがってたファイルの中身」が書かれている場所のこと。 クライアントがサーバーから送信されたデータを受け取るための部分であり、そのデータはHTTPレスポンスの目的や内容に応じて異なる。

## JSONとは
JavaScript Object Notationの略で、JavaScriptというプログラミング言語におけるオブジェクトの書き方を参考に作られたデータフォーマット(データの記述形式)のこと。
JSONはもともとJavaScriptで使用することを想定して開発された。しかし、人間とコンピューターの双方にとって可読性が高く、データが重くなりづらいという優れた特徴を持つため、現在はJavaScriptに限らずPythonやPHPなど多様な言語で用いられている。

### JSONデータを使った例
```json
{
 "name": "KANA",
 "job": "SE",
 "id": "201",
 "createdAt": "2024-03-30",
 "contactdetails": {
  "phone": "09000000000000",
  "email": "raise.tech.java@"
 }
}
```

このJSONデータには、ユーザーの情報が含まれている。具体的には、名前 、職業、ID、作成日時、電話番号、メールアドレスが含まれている。
