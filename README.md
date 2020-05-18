# README

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
