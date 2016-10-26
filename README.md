# git-practice
朝食と昼食まとめ用リポジトリ

- [朝食リポジトリ](https://github.com/matsuo-y/git-practice-breakfast)
- [朝食本番環境](https://matsuo-y.github.io/git-practice-breakfast/)
- [昼食リポジトリ](https://github.com/matsuo-y/git-practice-lunch)
- [昼食本番環境](https://matsuo-y.github.io/git-practice-lunch/)

issue用ブランチはstagingブランチから切る

## 朝食リポジトリ
`アプリ内書店の開発のように、リリースまでの開発期間が長いブランチ戦略`
- issue作成者：朝食リポジトリでのissue作成、issue用ブランチへのPRレビュー(最低1回は修正依頼を出す)、staging・masterブランチへのPR作成を行う
- branch作成者：issueが発行された後、stagingブランチからissue用ブランチを作成する
- PR担当者(朝食報告、2名)：issue用ブランチから作業用ブランチを作成し、issue用ブランチへのPRを作成する
- リリース担当者：staging・masterブランチへのリリース(PRレビュー)を行う、masterブランチへマージ後にデプロイタスクを実行(今回はherokuやgithubが自動実行)し、releases/tagsの設定を行う

## 昼食リポジトリ
`開発内容を即時リリースするように、リリースまでの開発期間が短いブランチ戦略`
- issue作成者：昼食リポジトリでのissue作成、stagingブランチへのPRレビュー(最低1回は修正依頼を出す)、masterブランチへのPR作成を行う
- PR担当者(昼食報告、1名)：stagingブランチからissue用ブランチを作成して作業を行い、stagingブランチへのPRを作成する
- リリース担当者：staging・masterブランチへのリリース(PRレビュー)を行う、masterブランチへマージ後にデプロイタスクを実行(今回はherokuやgithubが自動実行)し、releases/tagsの設定を行う

※昼食でのstagingブランチへのPRレビュー順
【issue用ブランチ】
↓[issue作成者レビュー(PRでレビューした旨のコメント記載)]
↓[リリース担当者レビュー(PRマージ実行)]
【stagingブランチ】

# heroku

## 朝食

- review app環境(PRごとに作成)：https://git-practice-breakfast-pr-{N}.herokuapp.com/
- ステージング環境(対象ブランチ：matsuo-y/git-practice-breakfastのstaging)：https://staging-git-practice-breakfast.herokuapp.com/
- 本番環境(対象ブランチ：matsuo-y/git-practice-breakfastのmaster)：https://git-practice-breakfast.herokuapp.com/

## 昼食

- review app環境(PRごとに作成)：https://git-practice-lunch-pr-{N}.herokuapp.com/
- ステージング環境(対象ブランチ：matsuo-y/git-practice-lunchのstaging)：https://staging-git-practice-lunch.herokuapp.com/
- 本番環境(対象ブランチ：matsuo-y/git-practice-lunchのmaster)：https://git-practice-lunch.herokuapp.com/