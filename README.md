# techdojo-monitoring-sample
## 概要
### イベント
本repositoryは、以下イベントの際に使用するデモ環境起動用ファイル群になります。<br>
https://ibm-developer.connpass.com/event/278896/

### デモ内容
* Prometheus（Grafana）でPostgreSQLを監視する
* PostgreSQLコンテナを停止して、メールアラートがくることを確認

### システム構成図
![システム構成図](https://github.com/NoriMuraZ/techdojo-monitoring-sample/assets/99166088/058974e6-9f64-48c2-a576-0e32e4bdf0fc)

### フォルダ構成
以下のような構成になります。
```
|-data
|-proc
|-rootfs
|-sys
|-prometheus---prometheus.yml
             |-rules.yml
|-alertmanager---config.yml
|-docker-compose.yml
|-Postgresql_Instance_Health.json
|-postgres.env

```

### ファイル構成
* docker-compose.yml：デモするコンテナ環境
* postgres.env：postgres-expoterのデータベース接続設定ファイル）
* prometheus/prometheus.yml：prometheus本体の設定ファイル
* prometheus/rules.yml：アラート条件設定ファイル
* alertmanager/config.yml：アラート通知先設定ファイル
* Postgresql_Instance_Health.json：Grafana用Postgresqlダッシュボードファイル

## 動作確認環境
* Windows11
* Docker for Business

## 起動方法
➀任意のフォルダにすべてダウンロード

➁同じフォルダ内に以下4つのフォルダを作成する
```
$ mkdir data
$ mkdir proc
$ mkdir rootfs
$ mkdir sys
```

➂以下コマンドを実行
```
$ docker-compose up -d
```

## 動作確認
以下URLにアクセスしてadmin/adminでログイン
```
http://locaohost:3003
```
