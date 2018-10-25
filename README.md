DockerでSFTP/FTPS/FTPサーバーを起動するための`docker-compose.yml`の例です。
テストのみに利用ください。

# 使い方

```bash
# 開始
docker-compose up -d

# 終了
docker-compose down
```

# 共通の仕様

* ホスト: localhost
* ローカルディレクトリ: ./remote

ローカルの`./remote`がリモートの`./remote`に接続されます。

# SFTP(パスワード認証)

* ポート: 10220
* ユーザ名: sftp-without-key
* パスワード: pass
* リモートディレクトリ(フルパス): /home/sftp-without-key/remote

# SFTP(RSA公開鍵認証)

* ポート: 10221
* ユーザ名: sftp-with-rsa-key
* リモートディレクトリ(フルパス): /home/sftp-with-rsa-key/remote
* 秘密鍵: ./ssh/id_rsa

# SFTP(ED25519公開鍵認証)

* ポート: 10222
* ユーザ名: sftp-with-ed25519-key
* リモートディレクトリ(フルパス): /home/sftp-with-ed25519-key/remote
* 秘密鍵: ./ssh/id_ed25519

# FTP

* ポート: 10210
* ユーザ名: ftp
* パスワード: pass
* リモートディレクトリ(フルパス): /home/virtual/ftp/remote

# FTPS

TLSエラーが発生するので無視してください。

* ポート: 10211
* ユーザ名: ftps
* パスワード: pass
* リモートディレクトリ(フルパス): /home/virtual/ftps/remote

# プルリク歓迎

* FTPSのTLS証明書
* WebDAVなど他のプロトコル