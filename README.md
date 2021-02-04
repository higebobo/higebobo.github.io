# README

## セットアップ

### サイト作成

```shell
npx gatsby new mate-portfolio https://github.com/EmaSuriano/gatsby-starter-mate
```

### Contentful側の準備

APIトークン作成

* `Settigs>API Keys>Content delivery / preview tokens`
* `Settigs>API Keys>Content management tokens` (上記と別タブ)
    * **Manage Tokenはアカウントのトークン(SpaceID固有ではないj)**
    * **作成時にしかコピーできないので注意**

設定

```shell
yarn setup
```

.envに以下が設定される

* `SPACE_ID`
* `ACCESS_TOKEN` (delivery token)

起動

```shell
yarn start
```

## 備考

* Github Pagesで運用する場合
    * Github>Settings>Secrets (**Environmentsではない**)
