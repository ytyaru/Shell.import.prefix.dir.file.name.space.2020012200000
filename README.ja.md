[en](./README.md)

# Import on Bash 4

　Bashファイルをインポートします。

# 特徴

* プレフィックスとしてファイルとディレクトリ名を追加する
    * それらにスペースが含まれるとき、ハイフンに変換する

```sh
. ./moduled_import.sh 'di r/fi le.sh'
di-r.fi-le.func
```

# 開発環境

* <time datetime="2020-01-18T15:11:55+0900">2020-01-18</time>
* [Raspbierry Pi](https://ja.wikipedia.org/wiki/Raspberry_Pi) 4 Model B Rev 1.2
* [Raspbian](https://ja.wikipedia.org/wiki/Raspbian) buster 10.0 2019-09-26 <small>[setup](http://ytyaru.hatenablog.com/entry/2019/12/25/222222)</small>
* bash 5.0.3(1)-release

```sh
$ uname -a
Linux raspberrypi 4.19.75-v7l+ #1270 SMP Tue Sep 24 18:51:41 BST 2019 armv7l GNU/Linux
```

# インストール

```sh
git clone https://github.com/ytyaru/Shell.import.prefix.dir.file.name.space.2020012200000
```

# 使い方

```sh
cd /src
./main.sh
```

## `import`の準備

1. `moduled_import.sh`ファイルを`import`にリネームする
2. `import`ファイルを環境変数`PATH`に通す

## `import`の呼出例

* some_dir/
    * main.sh
    * sub/
        * lib.sh
    * su b/
        * li b.sh

sub/lib.sh
```sh
Func() { echo 'Called sub/lib.sh Func()'; }
```
su b/li b.sh
```sh
Func() { echo 'Called "su b/li b.sh" Func()'; }
```
main.sh
```sh
. import sub/lib.sh
. import 'su b/li b.sh'
sub.lib.Func
su-b.li-b.Func
```

# 注意

* `import`自体を`.`(`source`)コマンドで読み込む必要がある
* プレフィクスを変更できない
    * プレフィクスを無しにしたい
    * プレフィクスを指定した階層まで付与したい
    * プレフィクスを指定したい（別名定義）
* インポートのルートディレクトリは`import`呼出元ファイルが存在するディレクトリです

# 著者

　ytyaru

* [![github](http://www.google.com/s2/favicons?domain=github.com)](https://github.com/ytyaru "github")
* [![hatena](http://www.google.com/s2/favicons?domain=www.hatena.ne.jp)](http://ytyaru.hatenablog.com/ytyaru "hatena")
* [![mastodon](http://www.google.com/s2/favicons?domain=mstdn.jp)](https://mstdn.jp/web/accounts/233143 "mastdon")

# ライセンス

　このソフトウェアはCC0ライセンスである。

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")](http://creativecommons.org/publicdomain/zero/1.0/deed.ja)

