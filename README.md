# l4cc
[低レイヤを知りたい人のためのCコンパイラ作成入門](https://www.sigbus.info/compilerbook/)の学習管理リポジトリ

## メモ

### CPUとメモリ

CPUが実行するプログラムと、そのプログラムが扱うデータは、どちらもメモリに入っていて、CPUはメモリから順に機械語命令を読み、その命令を実行する

CPUにはレジスタという小さな記憶領域があり、多くのCPU命令はレジスタ間での操作として定義されている


### アセンブラ

CPUが実行するプログラムの形式そのもののことを「機械語」と言う。

アセンブリは機械語にほぼそのまま1対1で対応するような言語。

アセンブリ言語で書いたプログラムを機械語プログラムに変換することをアセンブルすると言う。また、それを行うプログラムのことをアセンブラと言う。

機械語を直接出力しているように見えるコンパイラも、普通の構成では、アセンブリを出力したあとにバックグラウンドでアセンブラを起動している。本書で作るCコンパイラの出力もアセンブリとなる。

Cコンパイラは、test1.cのようなCコードを読み込んで、test2.sのようなアセンブリを出力するプログラムとなる。

#### レジスタ

| 項目  | 説明 |
| ------------- | ------------- |
| RDIレジスタ | 第一引数 |
| RSIレジスタ | 第二引数 |
| RDXレジスタ | 第三引数 |
| RAXレジスタ | 整数を入れられ、関数からリターンしたときにRAXに入っている値が関数の返り値となる |

### 再帰下降構文解析
1つの生成規則を1つの関数にマップするという構文解析の手法のことをいう。


## 環境構築

```
$ git clone https://github.com/rikoroku/l4cc.git
$ cd l4cc
$ docker-compose build
```

## 開発

```
$ docker-compose up -d && docker-compose exec l4cc bash
$ docker-compose stop
```

### テスト

```
$ make test
```

## 進捗管理
[現在進行中のアンカーリンク](https://www.sigbus.info/compilerbook/#スタックマシン)
