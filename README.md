# README

* contentful:space:gatsby-mate使用
* gatsby-mateのユーザレポジトリ版(masterブランチに出力)

## Setup

サイト作成

```shell
npx gatsby new gatsby-mate https://github.com/EmaSuriano/gatsby-starter-mate
```

### Spaceの作成

1. Contentful(https://www.contentful.com/)にGithubアカンとでログインし"gatsby-mate"というspaceを作成
2. Settings>API KeysでContent management tokensタブからPersonal access tokensを生成
    * Name: gatsby-mate
    * これがmanagement tokenとなる(**生成後は確認できないのでコピーしておく**)
3. Settings>API Keys>Content delivery / preview tokens>Add API Key>Add API Keyで生成
    * Name: gatsby-mate

### セットアップ

以下を準備

* Space ID
* Content Delivery API access token
* Content Management API access token

```shell
npm run setup
```

開発サーバ起動

```shell
gatsby develop
```

## Github連携

Settngs>Secretsに以下を登録(.envと同じ)

* SPACE_ID
* ACCESS_TOKEN

gh_pages.yaml

```yaml
    - name: build
      env:
        SPACE_ID: ${{ secrets.SPACE_ID }}
        ACCESS_TOKEN: ${{ secrets.ACCESS_TOKEN }}
      run: npm run build
```

username.github.ioで公開する場合はmasterブランチを出力先にするため別ブランチで作業

```shell
git branch -m master source
git push -u origin source
```

Settigs>Branches>Default branchでsourceを指定

## Link

* [rohitguptab/rg\-portfolio: This is repository create for Portfolio website starter](https://github.com/rohitguptab/rg-portfolio)
* [Import and Export data with contentful\-cli \| Rohit Gupta](https://rohitgupta.design/import-and-export-data-with-contentful-cli)
* [ソースコードを source ブランチで管理するためブランチ名をリネーム](https://ks6088ts.github.io/20200307-gatsby-get-started/)
* [GitHub Actions による GitHub Pages への自動デプロイ \- Qiita](https://qiita.com/peaceiris/items/d401f2e5724fdcb0759d)
* [How to Change 'gatsby build' directory？ · Issue \#18975 · gatsbyjs/gatsby](https://github.com/gatsbyjs/gatsby/issues/18975)
