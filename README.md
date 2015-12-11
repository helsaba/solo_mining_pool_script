#monacoinの俺々プールを楽ちんに構築する
そんな感じのスクリプト。

全体的にてきとうに作っているので何が起こっても責任は取りません。

テストしてるの環境はUbuntu14.04.3 64bitです。他は知りません。

##使い方
1. cloneしてくる
2. script.shを実行する
3. 各種情報入力
4. 再起動
5. ログインするとプール始動

勿論monacoindがネットワークに同期が完了するまでは掘れないです。

ログインしないとプール（monacoind, NOMP）は起動しないので、Ubuntuのインストールの時に自動ログインを有効にしておくといいかも知れません。

##各種情報について
|||
|---|---:|
|rpcuser|好きに決めよう|
|rpcpassword|好きに決めよう|
|rpcallowip|127.0.0.1にしよう|
|rpcport|何でもいいけど、被りが無いようにするのとそれなりに大きな数字にしておこう（てきとう）|
|web port|何でもいいけど、被りが無いようにするのとそれなりに大きな数字にしておこう|
|stratumHost|GettingStartedで表示されるホスト名、表示に関わる部分なのでぶっちゃけどうでｍ（ｒｙ|
|minimumPayment|払い出し最少額|
|initial_Diff|接続直後の初期Diff|
|minimum_Diff|Diffの最小値|
|maximum_Diff|Diffの最大値|

##マイニングする
- URLはstratum+tcp://IPアドレスなりなんなり:3032といった感じ
- ポート番号は~/nomp/pool_configs/monacoin.jsonの下の方で定義されています
- ユーザ名には報酬を受け取るアドレスを指定
- パスワードは適当に（決まってない）

###外からマイニングする
- クラウドマイニングとかで使えますね
- 適切なポート（そのまんま導入すれば3032）を適宜開放してやれば外からでもマイニングできます

##これからやろうと思うこと
- Default値を決めておく（空白だった場合に値を入れる）
- きちんとエラーを拾う
