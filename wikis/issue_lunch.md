# タイトル

 - {YYYY.mm.dd} {name}さんlunch

# 内容
## 作業内容

 mm/ddの〇〇さんの昼ごはんを以下のサイトで公開できる。

 branch作成以降の実際の開発タスクについては、[ebook-okazaki/git-training-lunch](https://github.com/ebook-okazaki/git-training-lunch)リポジトリで行う。

 - ebook-okazaki/git-training-lunchリポジトリにはissueを作成しない。
 - ebook-okazaki/git-training-lunchリポジトリ内に作成したPRは、ebook-okazaki/git-trainingリポジトリのissueにconnectさせる。

 `git-training/#{N}-{name}-lunch` ブランチで作業を行い、`origin/master` ブランチへPRしてマージする。

 コミットメッセージは、 `ebook-okazaki/git-training#{N} 誰の昼食か（どんな修正か）` の形式にする。

 PRのタイトルは、
 - `git-training/#{N}-{name}-lunchからmasterへのマージ(git-training/#{N})`
 以上の形式とする

## 開発時に使用する環境

 |環境|URL|
 |---|---|
 |PR環境|https://git-training-lunch-oka-pr-{N}.herokuapp.com/|
 |本番環境|https://git-training-lunch-oka.herokuapp.com/|

 - PR時にはPR番号{N}の環境をブラウザで確認する

## 作業担当者の割り当て

 - issue作成者：◇◇
 - branch作成者：〇〇
 - 開発担当者(昼食報告、1名)：〇〇
 - 検収担当者：◇◇
 - リリース担当者：〇〇

## 判定基準

 - [ ] issue作成者が、issueを作成した
 - [ ] branch作成者が、issue branchを作成した
 - [ ] 開発担当者が、master branchへのPRを作成した
 - [ ] 検収担当者が、master branchへのPRをマージ完了した
 - [ ] リリース担当者が、master branchのHEADに対して、releases/tagsを設定し、issueに記載した
 - [ ] リリース担当者が、master branch がデプロイされた結果を確認し、issueに確認した結果を記載した
 - [ ] 検収担当者が、issueをcloseした