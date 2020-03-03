# ONT エクスチェンジに関するFAQ

## Q： Ontology ノードはどのようにしてポラリスのテストネット（polaris TestNet）に接続していますか

A:ノードが始動している際にパラメーターが追加されます : ```--networkid 2``` . 
詳細はこのページをご参照ください ```./ontology --help```


## Q: 取引手数料とは?

A: 取引ごとに Ontology ネットワークのONG (gas)が消費されます。 500を超える取引のみがメインネット （MainNet）にパッケージ化されます。

```gasprice * gaslimit = ong  cost```


ガスリミット（gaslimit）の最小値は20000でガスプライス（gasprice）の最小値は500です。したがって、一般的に言うと、最小限の取引は 0.01 ONGとなります。複雑なコントラクトである場合、ガスリミット（gaslimit）の最小値が20000より低くなる可能性があります。ガスプライス（gasprice）はユーザーによって設定されますが、最小値より大きく設定するようお願い申し上げます。


## Q: ONTはどのようにしてONGをアンバインドにしますか?

A: 初期段階ではすべてのONGはONTシステムのコントラクトアドレスに送信され、ONGは時間の経過とともにだんだんにアンバインドされるようになります。アンバインドのONGのアドレスは唯一で固定されています。

## Q: ONTとONGの小数の量に関する問題

A: ONTの小数の量は0で分けられません。ONGの10進数は9で分けられます。 取引手数料はONGによって支払われます。


## Q: 取引には取引コストが計算される場合、取引料金は振替トランザクションにも対応します。振替された取引はどのようにして識別しますか。振替先は固定なアドレスですか。

A: 総計取引手数料は最新のプッシュ通知の **gasConsumed** でチェックできます。料金はガバナンスコントラクトのアドレスに振替します。アドレス: AFmseVrdL9f9oyCzZefL9tG6UbviEH9ugK。このアドレスは唯一です。


## Q: 特別なコントラクトアドレスに関する説明

A:

| 名称   | アドレス(Hex)                         | アドレス(Base58)                |
| -------- | ---------------------------------------- | ---------------------------------- |
| ONT      | 0100000000000000000000000000000000000000 | AFmseVrdL9f9oyCzZefL9tG6UbvhUMqNMV |
| ONG      | 0200000000000000000000000000000000000000 | AFmseVrdL9f9oyCzZefL9tG6UbvhfRZMHJ |
| Governance Contract | 0700000000000000000000000000000000000000 | AFmseVrdL9f9oyCzZefL9tG6UbviEH9ugK |

## Q: ONTブロックチェーンのエクスポーラーはどこにありますか?
A:[https://explorer.ont.io/](https://explorer.ont.io/)


## Q: 「ホワイトリストスタートアップ（White list startup）」とは？
A: 汚染されたノードや悪意ノードとの同期化を回避するためにホワイトリストスタートアップを利用し、公式のシードノードを直接に同期化することができます。コマンド:
``` ./ontology --reserved-file=./peers.rsv --reserved-only``` 
ホワイトリストファイル peers.rsv は鉾のところで提供いたします。 

## Q: NEP-5 ONT トークンの交換方法

 2018.10.1まで 

1. お客様はNEP-5 ONT トークンを破棄アドレスに振替するようお願い申し上げます。アドレス :AFmseVrdL9f9oyCzZefL9tG6UbvhPbdYzM

2. メールを送信してください。 送信先: xiaomin@ont.io;wengjunjie@ont.io;zhoupeiwen@ont.io 。下記の様式でお願いいたします。

   エクスチェンジ　ネーム（Exchange Name）:

   トークンのスワップ数量（Token swap amount）:

   振替取引ハッシュ（Transfer transaction hash）:

3. 1日以内にメインネット（mainnet） ONTは元のアドレスに戻ります。確認メールも共に送信いたします。

## Q: トークンのスワップはどのようにしてongが発行されますか

1. トークンのスワップ中に発行されたongs数量 :  処理時間 (最大24時間)を除き、 Ontology のメインネットが起動してからnep-5 コインが破棄アドレスに振替されたまでのongsは無制限です。

2. ユーザーへのong分配:ong振替とontは同じで最低0.01 ongが消耗されます。

3. ongsをおとす場合、毎回の操作ごとに同じな手数料が消費されますので頻繁に引き出すことはお勧めしません。 

## Q:ONG無制限ルールとは？
ONG引出可能の数量 = [1秒あたりの無制限ong数量] × [ONTの保有時間] × [ONTの保有量] / [ONT総供給]

[1秒あたりの無制限ong数量] は [5, 4, 3, 3, 2, 2, 2, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]  毎年ずつ減少されます。

[ONTの保有時間] : 現在の時刻 - ONTアカウントの最後変更時刻 

[ONT総供給] : 1000000000

例えば:アカウント Aは1日目に100 ONTsを保有し、 2日目に200 ONTs と3日目に 300 ONTsを保有しています。 引出可能のONGsは下記のようになっています。

（24×60×60)×5×100/1000000000 + （24×60×60)×5×200/1000000000

ほかの300 ONTsは次のアカウントのONTsが変更された際に計算されます。 

The first アカウントのONT の最初変更時刻は2018/6/30の Ontology メインネットの起動時刻です。
