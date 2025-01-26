```sh
❯ kamal init
Created configuration file in config/deploy.yml
Created .kamal/secrets file
Created sample hooks in .kamal/hooks
```

Kamal を使用して何かをデプロイするには、 /upヘルスチェック ルート (成功した200ステータス コードを返す単純なエンドポイント)を使用してポート80でアプリケーション サーバーを実行する Dockerfile が必要です。


❯ export KAMAL_REGISTRY_PASSWORD=dckr_pat_UhVWyIGaYq63CLg_E-iund4aAXQ


ドメイン名を VM ホスト名として使用しないでください。このホスト名は/etc/resolv.confファイルの一部となり、アプリケーションから完全なドメイン名を参照するときにローカル ルーティングが上書きされます。



  INFO [09d34ac2] Running docker buildx build --push --platform linux/amd64 --builder kamal-local-docker-container -t thr3a/nextjs-template:f7dd04b050320400454e2c5f7a131e43521eea06 -t thr3a/nextjs-template:latest --label service="nextjs-template" --file Dockerfile . as thr3a@localhost

kamal setup



サポートされているプロキシ機能は次のとおりです。

​▪​

提供されたホストに基づくルーティング
​▪​

Let's Encrypt による自動 TLS 証明書
​▪​

リクエストとレスポンスのバッファリング
​▪​

最大リクエストおよび応答サイズ


[https://github.com/basecamp/kamal/issues/330:embed:cite]

```sh
  INFO [d9b6247b] Finished in 0.457 seconds with exit status 0 (successful).
  Finished all in 92.6 seconds
Releasing the deploy lock...
  Finished all in 93.1 seconds
  ERROR (SSHKit::Command::Failed): Exception while executing on host 192.168.16.12: docker exit status: 1
docker stdout: Nothing written
docker stderr: Error: target failed to become healthy within configured timeout (30s)
```

❯ cat .zshenv 
#
# Defines environment variables.
#
# Authors:
#   Sorin Ionescu <sorin.ionescu@gmail.com>
#

# Ensure that a non-login, non-interactive shell has a defined environment.
if [[ ( "$SHLVL" -eq 1 && ! -o LOGIN ) && -s "${ZDOTDIR:-$HOME}/.zprofile" ]]; then
  source "${ZDOTDIR:-$HOME}/.zprofile"
fi

setopt +o nomatch



```
  INFO [732077b2] Running docker container ls --all --filter name=^fastapi-template-web-3d5ece342b4c05381fd1b1bb9f29846d507ae5a4$ --quiet | xargs docker stop on 192.168.16.12
  INFO [732077b2] Finished in 0.501 seconds with exit status 0 (successful).
  Finished all in 78.9 seconds
Releasing the deploy lock...
  Finished all in 79.4 seconds
  ERROR (SSHKit::Command::Failed): Exception while executing on host 192.168.16.12: docker exit status: 1
docker stdout: Nothing written
docker stderr: Error: target failed to become healthy within configured timeout (30s)
```


```
  INFO [bb45e5a4] Finished in 0.091 seconds with exit status 0 (successful).
  Finished all in 40.4 seconds
Releasing the deploy lock...
  Finished all in 40.8 seconds
```


```
root@ubuntu02:~# docker ps|grep kamal
b54cbf36dc74   basecamp/kamal-proxy:v0.8.4                                       "kamal-proxy run"         47 minutes ago   Up 47 minutes          0.0.0.0:80->80/tcp, :::80->80/tcp, 0.0.0.0:443->443/tcp, :::443->443/tcp   kamal-proxy
```
