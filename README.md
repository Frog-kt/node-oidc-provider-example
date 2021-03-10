# node-oidc-provider-example

https://github.com/panva/node-oidc-provider-example

herokuでoidc-providerのサンプルプロジェクトをデプロイしてみました。

DBにはRedisを使用

## 立ち上げ方

```bash
heroku create --addons securekey,heroku-redis:hobby-dev

heroku labs:enable runtime-dyno-metadata

heroku config | grep REDIS_URL

git add .
git commit -a -m 'added a redis adapter for persisting data'

git push heroku main
```

uriの例
```
https://example.com/auth?client_id=foo&response_type=id_token&redirect_uri=https%3A%2F%2Fjwt.io&scope=openid%20email&nonce=foobar&prompt=login
```