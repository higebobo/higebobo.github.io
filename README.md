# README

* contentful:space:gatsby-mate 使用
* gatsby-mate のユーザレポジトリ版(master ブランチに出力)

## セットアップ

### サイト作成

```shell
npx gatsby new mate-portfolio https://github.com/EmaSuriano/gatsby-starter-mate
```

### Contentful側の準備

#### Space の作成

1. Contentful(https://www.contentful.com/) に Github アカンとでログインし"gatsby-mate"という space を作成
2. Settings>API Keys で Content management tokens タブから Personal access tokens を生成
    * Name: gatsby-mate
    * これが management token となる
        * **生成後は確認できないのでコピーしておく**
        * **Manage Tokenはアカウントのトークン(SpaceID固有ではないj)**
3. Settings>API Keys>Content delivery / preview tokens>Add API Key>Add API Key で生成
    *  Name: gatsby-mate

### 設定

以下を準備

* Space ID
* Content Delivery API access token
* Content Management API access token

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

Github Pagesで運用する場合

* Github>Settings>Secrets (**Environmentsではない**)

username.github.io で公開する場合は master ブランチを出力先にするため別ブランチで作業

```shell
git branch -m master source
git push -u origin source
```

Settigs>Branches>Default branch で source を指定

## Link

- [rohitguptab/rg\-portfolio: This is repository create for Portfolio website starter](https://github.com/rohitguptab/rg-portfolio)
- [Import and Export data with contentful\-cli \| Rohit Gupta](https://rohitgupta.design/import-and-export-data-with-contentful-cli)
- [ソースコードを source ブランチで管理するためブランチ名をリネーム](https://ks6088ts.github.io/20200307-gatsby-get-started/)
- [GitHub Actions による GitHub Pages への自動デプロイ \- Qiita](https://qiita.com/peaceiris/items/d401f2e5724fdcb0759d)
- [How to Change 'gatsby build' directory？ · Issue \#18975 · gatsbyjs/gatsby](https://github.com/gatsbyjs/gatsby/issues/18975)
- [VSCode で gatsby のデバッグをする \- Qiita](https://qiita.com/3S_Laboo/items/8a963cd87d917a8bd3c9)
