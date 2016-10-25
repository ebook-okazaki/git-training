# git-practice
朝食と昼食まとめ用リポジトリ

- [朝食リポジトリ](https://github.com/matsuo-y/git-practice-breakfast)
- [朝食本番環境](https://matsuo-y.github.io/git-practice-breakfast/)
- [昼食リポジトリ](https://github.com/matsuo-y/git-practice-lunch)
- [昼食本番環境](https://matsuo-y.github.io/git-practice-lunch/)

issue用ブランチはstagingから切る

## 朝食リポジトリ
`アプリ内書店の開発のように、リリースまでの開発期間が長いブランチ戦略`
- issue作成者：issue用ブランチへのPRレビュー(最低1回は修正依頼を出す)、staging・masterへのPR作成を行う
- branch作成者：issueが発行された後、stagingからissue用ブランチを作成する
- PR担当者(朝食報告、2名)：issue用ブランチから作業用ブランチを作成し、issue用ブランチへのPRを作成する
- リリース担当者：staging・masterへのリリース(PRレビュー)を行う

## 昼食リポジトリ
`開発内容を即時リリースするように、リリースまでの開発期間が短いブランチ戦略`
- issue作成者：issue用ブランチへのPRレビュー(最低1回は修正依頼を出す)、staging・masterへのPR作成を行う
- branch作成者：issueが発行された後、stagingからissue用ブランチを作成する
- PR担当者(昼食報告、1名)：issue用ブランチから作業用ブランチを作成し、issue用ブランチへのPRを作成する
- リリース担当者：staging・masterへのリリース(PRレビュー)を行う

# heroku

## 朝食

- review app環境(PRごとに作成)：https://git-practice-breakfast-pr-{N}.herokuapp.com/
- ステージング環境(対象ブランチ：matsuo-y/git-practice-breakfastのstaging)：https://staging-git-practice-breakfast.herokuapp.com/
- 本番環境(対象ブランチ：matsuo-y/git-practice-breakfastのmaster)：https://git-practice-breakfast.herokuapp.com/

## 昼食

- review app環境(PRごとに作成)：https://git-practice-lunch-pr-{N}.herokuapp.com/
- ステージング環境(対象ブランチ：matsuo-y/git-practice-lunchのstaging)：https://staging-git-practice-lunch.herokuapp.com/
- 本番環境(対象ブランチ：matsuo-y/git-practice-lunchのmaster)：https://git-practice-lunch.herokuapp.com/