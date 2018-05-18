# git-practice
## 朝食と昼食のまとめ用リポジトリ

 - [朝食リポジトリ](https://github.com/ebook-okazaki/git-training-breakfast)
 - [朝食本番環境(github)](https://git-training-breakfast-oka.herokuapp.com/)
 - [昼食リポジトリ](https://github.com/ebook-okazaki/git-training-lunch)
 - [昼食本番環境(github)](https://git-training-lunch-oka.herokuapp.com/)
 - [waffleかんばん](https://waffle.io/ebook-okazaki/git-training)

# ブランチについて
## ブランチの種類
### 本番 `eBookJapan`

 - master branch：本番環境にデプロイするコードを格納するブランチ
 - staging branch：staging環境にデプロイするコードを格納するブランチ
 - issue branch：staging branchを起点とし、issueの開発を実装したコードを格納するブランチ
 - issue child branch：issue branchを起点とし、issueの開発に関する小さな単位の機能を実装したコードを格納するブランチ

### 朝食・昼食 `Git練習環境`

 - master branch：本番環境にデプロイするコードを格納するブランチ
 - issue branch：master branchを起点とし、issueの開発を実装したコードを格納するブランチ
 - issue child branch：issue branchを起点とし、issueの開発に関する小さな単位の機能を実装したコードを格納するブランチ

## ブランチの初期設定

 - master branch
   - github.com リポジトリの設定で、誰かが誤って削除しないように、force pushしないように、プロテクトする
   - github.com リポジトリの設定で、誰かが直接コミットしないように、PRを通して、マージするように設定する
 - staging branch (朝食・昼食では使用しておりません)
   - github.com リポジトリの設定で、誰かが誤って削除しないように、force pushしないように、プロテクトする
   - github.com リポジトリの設定で、誰かが直接コミットしないように、PRを通して、マージするように設定する

## ブランチのマージルール

 - master branchは、issue branchからのPRのみを受け付ける
 - issue branchは、issue child branchからのPRを受け付ける

## ブランチの運用ルール

 - master branch から、 issue branch を分岐する(checkout)
 - issue branch から、issue child branch を分岐する (checkout)
 - 朝食の場合
   - 1日目
     - issue branchにマージコミットが発生した場合、存在するissue child branch はissue branchの変更分のコミットを取り込む（mergeする）
   - 2日目
     - issue branchにマージコミットが発生した場合、存在するissue child branch はissue branchの変更分のコミットを取り込む（rebaseする）

# 各リポジトリについて
## 朝食リポジトリ

 `アプリ内書店の開発のように、リリースまでの開発期間が長いブランチ戦略`

 - issue作成者
   - git-trainingリポジトリでのissue作成
 - branch作成者
   - master branchからissue branchを作成
 ---
 ※2日間で作業を行います

 - 開発担当者(朝食報告:2日間、2名以上)
   - issue branchからissue child branchを作成
   - issue child branchで作業を行い、issue branchへのPRを作成
 - レビューア
   - issue branchへのPRをレビューし、マージする
   - コンフリクトした場合、開発担当者がissue child branchで解消する
     - 1日目はmergeで解消、2日目はrebaseで解消
 ---
 - リリース担当者
   - issue branchからmaster branchへのPRを作成
 - 検収担当者
   - master branchへのPRをレビューし、マージする
 - リリース担当者
   - デプロイされた結果を確認し、issueに確認した結果を記載
   - releases/tagsの設定を行う
 - 検収担当者
   - リリース担当者の記録を確認し、 issue をクローズ

## 昼食リポジトリ

 `開発内容を即時リリースするように、リリースまでの開発期間が短いブランチ戦略`
 - issue作成者
   - git-trainingリポジトリでのissue作成
 - branch作成者
   - master branchからissue branchを作成
 - 開発担当者(昼食報告、1名)
   - issue branchで作業を行い、master branchへのPRを作成
 - 検収担当者
   - master branchへのPRをレビューし、マージする
 - リリース担当者
   - デプロイされた結果を確認し、issueに確認した結果を記載
   - releases/tagsの設定を行う
 - 検収担当者
   - リリース担当者の記録を確認し、 issue をクローズ

# Herokuについて
## デプロイ環境

 - 朝食・昼食のデプロイにはHEROKUのフリー版（無料）を使用しています。
   - アプリの同時に起動する数は現状、5件という制限があります。
 - デプロイの画面が表示できない場合
   - MRを一度 `close` していただき、同時起動数を調整していただき、再度 `open` していただきますと使用できるようになります。
 - [Heroku](https://jp.heroku.com/)
 - [Herokuとは](https://tech-camp.in/note/technology/16108/)

## 朝食

 - review app環境(対象ブランチ：ebook-okazaki/git-training-breakfastのPRマージ元issue branch)：[https://git-training-breakfast-ok-pr-{N}.herokuapp.com/](https://git-training-breakfast-ok-pr-{N}.herokuapp.com/)
 - 本番環境(対象ブランチ：ebook-okazaki/git-training-breakfastのmaster branch)：[https://git-training-breakfast-oka.herokuapp.com/](https://git-training-breakfast-oka.herokuapp.com/)

## 昼食

 - review app環境(対象ブランチ：ebook-okazaki/git-training-lunchのPRマージ元issue branch)：[https://git-training-lunch-oka-pr-{N}.herokuapp.com/](https://git-training-lunch-oka-pr-{N}.herokuapp.com/)
 - 本番環境(対象ブランチ：ebook-okazaki/git-training-lunchのmaster branch)：[https://git-training-lunch-oka.herokuapp.com/](https://git-training-lunch-oka.herokuapp.com/)

# Git練習用 issue 例

 - [朝食１](https://github.com/ebook-okazaki/git-training/tree/master/wikis/issue_breakfast1.md)
   - Git練習 朝食用の issue 記載例 (ローカルとリモートで作業用ブランチ名が同じ)
 - [朝食２](https://github.com/ebook-okazaki/git-training/tree/master/wikis/issue_breakfast2.md)
   - Git練習 朝食用の issue 記載例 (ローカルとリモートで作業用ブランチ名が違う)
 - [昼食](https://github.com/ebook-okazaki/git-training/tree/master/wikis/issue_lunch.md)
   - Git練習 昼食用の issue 記載例
