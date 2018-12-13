# docker_vue_cli
Vue CLI を使うための Docker Compose です。

## 構成
```bash
.
├── app: Vue.js で作成したソースコードの共有ディレクトリ
└── docker_vue_cli: 本リポジトリの Docker Compose 環境ソースコード
```

## 使い方
```bash
git clone https://github.com/oki2a24/docker_vue_cli.git
cd docker_vue_cli
docker-compose up -d
docker-compose exec node bash
cat << EOF > hello.vue
<template>
  <p class="message">メッセージ: {{ msg }}</p>
</template>

<script>
export default {
  data () {
    return { msg: 'こんにちは！こんにちは！' }
  }
}
</script>

<style>
.message { color: #42b983; }
</style>
EOF
vue serve hello.vue
```

その後、Docker ホストマシンで、ウェブブラウザから http://localhost:8080 へアクセスし、ページが表示されることを確認してください。

## 補足
コンテナ起動後、コンテナに入らないで次のように操作することも可能です。

```bash
docker-compose up -d
docker-compose exec node vue serve hello.vue
 ```
