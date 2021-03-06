---
layout: content
title: データ型
prev: ファイルシステムの操作
next: データの読み込み
link_prev: /ja/moving_around.html
link_next: /ja/loading_data.html
---

従来、Unixシェルコマンドは文字列テキストを通じて互いに通信していました。あるコマンドは標準出力(しばしば'stdout'と略されます)を介してテキストを出力し、他方のコマンドは標準入力(または'stdin')を介してテキストを読み込みます。このようにして、２つのコマンドは通信できます。

この種の通信は文字列ベースと考えることができます。

Nuはコマンドに対してこのアプローチを採用しつつ、他の種類のデータを扱えるよう拡張しています。現在、Nuはシンプルなデータと構造化されたデータ、２つの種類をサポートしています。


## シンプルなデータ

多くのプログラミング言語と同様に、Nuはシンプルなデータと構造化されたデータを用いてデータをモデル化します。シンプルなデータ型には、整数、浮動小数点、文字列、真偽値、日付、およびパスが含まれます。ファイルサイズのための特別な型もこれに含まれます。

### 整数

整数(または丸めた数)。例として、１，５，および100があります。

### 浮動小数点

浮動小数点は小数部を含む数です。例として、1.5、2.0、および15.333があります。

### 文字列

文字列はテキストを表す基本的な方法です。文字列はダブルクォートを使って表されます。例として、"Fred", "myname.txt", and "Lynchburg, VA"があります。

Nuの文字列はデフォルトでUnicodeに対応しているためUTF-8のテキストを簡単に渡すことができます。

### 真偽値

真偽値は真か偽かの状態をとります。しばしば比較の結果を表すために使われます。

### 日付

日付と時間は日付型のデータに一緒に保持されます。システムで利用される日付データはタイムゾーンをもち、デフォルトではUTCタイムゾーンが使用されます。

### パス

パスは、特定のOSでファイルパスを表すプラットフォームに依存しない方法です。例として、`/usr/bin`や`C:\Users\file.txt`があげられます。

### バイト

ファイルサイズはバイトと呼ばれる特別な整数型で保持されます。例として、100, 15kb、100mbがあります。

## 構造化データ

構造化データはシンプルなデータから作られます。例えば、構造化データは、複数の整数を表す方法を提供します。現在サポートされている構造化データは次のとおりです。オブジェクト、バイナリーデータ、リスト、ブロック。

### オブジェクト

オブジェクトデータ型は、テーブルの１行に対応するデータを表現します。様々な要素をもち、各要素には列名があたえられます。

### バイナリーデータ

画像ファイルのデータと同様に、バイナリーデータは生のバイトの集まりです。

### リスト

リストは複数の値を保持できます。このことから、リストはテーブルの行を格納するコンテナに適しています。

### ブロック

ブロックはNuのコードブロックを表します。例えば、`where { $it.size > 10kb }`コマンドでは中括弧に含まれる`{ $it.size > 10kb }`部分がブロックです。ブロックはデータの各行で実行されるコードを表現する便利な方法です。