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
