
[![Build Status](https://travis-ci.org/osmfj/sotmjp2018.svg?branch=master)](https://travis-ci.org/osmfj/sotmjp2018)

# ローカル環境のセットアップ

Rubyが動作する環境が必要です。rbenvの利用が推奨されます。

```
gem install bundle
cd $PATH_TO_THIS_REPO
bundle install
```

# 開発

かならずトピックブランチを切って、変更をおこなってください。
Forkする必要はありません。githubのOSMFJ オーガニゼーション に所属していない関係者は、issueをあげてください。
変更内容は、Pull Request を発行し、github上でレビューをうけます。

プレビューは、以下のコマンドをローカルで実行してください。

```
bundle exec jekyll s
```

# デプロイ

masterブランチへのコミット結果は、Travisにより自動的にサイトに反映されます。
設定は、.travis.yml にあります。

自動スクリプトのポイントはつぎのとおりです。

* https://github.com/osmfj/stateofthemap リポジトリが公開用のリポジトリです

* travis コマンド による暗号化機能をもちいて、GH_TOKEN環境変数に、アクセストークンを埋め込みます。secure 行が該当します。

* `-b` オプションでbaseURLを指定する

```
bundle exec jekyll build -b 2018
```

* git push時に --quiet等をつけて、セキュリティ情報が公開されないようにしています。

* master ブランチのみで、実行されるようにしています。Pull Requestであやまって、更新されないようにしています。

# スポンサーの追加方法

## ロゴの配置

`assets/images/logo` にロゴのファイルを配置してください。PNG ファイルを想定しています。

## スポンサー情報の追加

`_data/sponsor.csv` にスポンサーの情報を追加します。エンコードは UTF-8、改行は LF です。  
第1カラムからスポンサーの名前、ウェブサイトの URL、ロゴのファイル名、スポンサーレベルをカンマで区切って入力します。  
新しく参加したスポンサーは最後の行に追加してください。

### スポンサーの名前

スポンサーの名前を入力します。日本語マルチバイト文字も使えます。`"`や`'`で囲う必要はありません。

### ウェブサイトの URL

スポンサーの URL を `http` や `https` から入力します。

### ロゴのファイル名

`assets/images/logo` に配置したロゴファイルのファイル名を入力します。  
ファイル名以外のパスは入力しないでください。
ロゴファイルが存在しない場合には空のセルにしておきます。

### スポンサーレベル

次のようにスポンサーのレベルを入力します。  
Gold なら gold  
Silver なら silver  
Personal Supporters なら support  

