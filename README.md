# Nuxt Practice
```
docker-compose up -d 
docker-compose exec nuxt_app sh
yarn create nuxt-app <project-name>
yarn dev
```

nuxtプロジェクトを表示されるためにはnuxt.config.jsに下記を追加

```
export default {
  // ここが追加されないといけないらしい
  // TODO: 原因はしっかり調べよう
  server: {
    port: 3000,
    host: '0.0.0.0'
  },
```