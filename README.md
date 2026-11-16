*This project has been created as part of the 42 curriculum by yukurosa.*

# NetPractice

## Description

NetPracticeは、実際のコンピュータネットワークを模したWeb上のシミュレーション環境を使用し、適切なネットワーク設定を行うことで、ネットワークの基礎知識を習得する課題です。

主に、IPアドレスやサブネットマスクによるネットワークの分割、スイッチとルーターの役割、ネットワークインターフェースの設定、ルーティングテーブルによる通信経路の制御について学びます。

全10レベルで指定された通信条件を満たすようにIPアドレスやルーティングを設定し、異なるネットワーク間でパケットが正しく送受信される仕組みを理解することを目的としています。

## Instructions

### インストールと起動

Python 3、Bash、およびWebブラウザを使用します。コンパイルは不要です。

42の課題ページから配布アーカイブをダウンロードし、任意の作業ディレクトリに配置します。ファイル名が `net_practice.1.10.tgz` の場合、ターミナルで以下のコマンドを実行します。配布ファイル名が異なる場合は読み替えてください。

```bash
# アーカイブを解凍
tar -xf net_practice.1.10.tgz

# 解凍されたディレクトリに移動
cd net_practice

# NetPracticeを起動
./run.sh
```

このリポジトリ内の展開済みの環境を使用する場合は、リポジトリ直下から `cd net_practice`、`./run.sh` を実行します。

`run.sh` はローカルWebサーバーを起動し、ブラウザでトレーニング画面を開きます。起動できない場合は、`net_practice` ディレクトリ内で以下を実行し、ブラウザで `http://localhost:49242` を開きます。

```bash
python3 -m http.server 49242
```

ポートが使用中の場合は別の番号を指定し、ブラウザのURLも同じ番号に変更してください。サーバーを停止するには、起動したターミナルで `Ctrl+C` を押します。

### トレーニングの開始

提出用の設定を作成するときは、開始画面に自分の42ログイン名（`yukurosa`）を入力します。ログイン名に対応する個人用の構成で、全10レベルに取り組みます。ランダムな構成で練習する場合は、`evaluation` タブも利用できます。

### 設定ファイルのエクスポート

各レベルでは、編集可能な欄のIPアドレス、サブネットマスク、ルーティングテーブルなどを設定し、画面上部に指定された通信条件を満たす必要があります。通信に失敗した場合は、画面下部のログで原因を確認できます。

設定が完了したら、以下の手順で設定ファイルを保存します。

1. `Check again` をクリックし、すべての通信目標が `OK` になっていることを確認する。
2. **次のレベルへ進む前に**、`Get my config` をクリックして設定ファイルをエクスポートする。
3. エクスポートしたファイルを、対応するレベルが分かる名前（`level1.json` など）で提出用Gitリポジトリのルート（直下）に保存する。
4. `Next level` で次のレベルに進み、全10レベルで同じ手順を繰り返す。

### 提出方法

全10レベルを完了し、`Get my config` からエクスポートした設定ファイルを**各レベルにつき1個、合計10個、提出用Gitリポジトリのルートに配置**します。`README.md` も同じ場所に置きます。

```text
.
├── README.md
├── level1.json
├── level2.json
├── level3.json
├── level4.json
├── level5.json
├── level6.json
├── level7.json
├── level8.json
├── level9.json
└── level10.json
```

提出前に、ファイル名と保存場所、全10レベル分がそろっていることを確認し、Gitにコミットして提出先へプッシュします。評価対象は提出リポジトリ内の成果物です。

### 相互評価

評価では、制限時間内にランダムな3レベルを解く必要があります。外部ツールの使用は認められていませんが、`bc` のような簡単な電卓は許可されています。

## Resources

### 参考資料

以下は、本課題で扱うネットワークの基礎知識を確認できる参考資料です。

- [ネットワークとは？わかりやすく仕組みや種類、構築方法を解説](https://www.qtpro.jp/blog/network/14.html)
- TCP/IP・デフォルトゲートウェイ・経路選択：[RFC 1122 — Requirements for Internet Hosts — Communication Layers](https://www.rfc-editor.org/rfc/rfc1122)（特に3.3.1節）
- サブネットマスク：[RFC 950 — Internet Standard Subnetting Procedure](https://www.rfc-editor.org/rfc/rfc950)
- CIDR：[RFC 4632 — Classless Inter-domain Routing (CIDR)](https://www.rfc-editor.org/rfc/rfc4632)
- ルーター：[Cloudflare — What is a router?](https://www.cloudflare.com/learning/network-layer/what-is-a-router/)
- スイッチとルーターの違い：[Cloudflare — What is a network switch?](https://www.cloudflare.com/learning/network-layer/what-is-a-network-switch/)
- OSI参照モデル：[Cloudflare — What is the OSI Model?](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)

### 学習したネットワークの概念

本課題では、主に以下のネットワーク技術について学習しました。

* TCP/IPアドレッシング：TCP/IPネットワークでIPアドレスを使ってインターフェースを識別し、通信先を指定する仕組み。本課題ではIPv4を扱う。
* サブネットマスク・CIDR：IPアドレスをネットワーク部とホスト部に分割し、ネットワークの範囲を定義する仕組み。
* デフォルトゲートウェイ：宛先に対するより具体的な経路がない場合に、パケットを転送する先のルーター。転送先には、直接接続されたネットワーク上で到達可能なルーターのIPアドレスを指定する。
* ルーター：異なるネットワーク間でパケットを転送するネットワーク機器。
* スイッチ：主に同一LAN内の機器を接続し、MACアドレスをもとにフレームを転送するネットワーク機器。
* ルーティングテーブル：宛先ネットワークに応じて、パケットの転送先を決定するための情報。
* OSI参照モデル：ネットワーク通信の機能を、物理層、データリンク層、ネットワーク層、トランスポート層、セッション層、プレゼンテーション層、アプリケーション層の7つに分類した概念モデル。一般的なL2スイッチは主に第2層、ルーターは第3層で動作する。

### AIの使用について

主に、AIは以下の目的で活用しました。

* IPアドレス、サブネットマスク、CIDRなどの基礎概念の理解。
* ルーター、スイッチ、デフォルトゲートウェイ、ルーティングテーブルの役割の整理。
* 通信エラーの原因や、パケットが送信元から宛先まで到達する仕組みの理解。
* READMEの文章構成や表現の改善、課題資料との要件の照合、および参考資料のリンクの補完。
