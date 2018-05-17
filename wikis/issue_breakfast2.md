# タイトル

 - {YYYY.mm.dd}-{YYYY.mm.dd} breakfast

# 内容
## 作業内容

 mm/dd-mm/ddの朝ごはんを以下のサイトで公開できる。

 branch作成以降の実際の開発タスクについては、[ebook-okazaki/git-training-breakfast](https://github.com/ebook-okazaki/git-training-breakfast)リポジトリで行う。

 - ebook-okazaki/git-training-breakfastリポジトリにはissueを作成しない。
 - ebook-okazaki/git-training-breakfastリポジトリ内に作成したPRは、ebook-okazaki/git-trainingリポジトリのissueにconnectさせる。

## 作業フロー

 1. branch 作成者はローカルリポジトリの master ブランチをチェックアウトする。リモートリポジトリの master ブランチをプルして、ローカルリポジトリの master ブランチへリモートリポジトリの master ブランチの最新コミットの取得と反映を行う。ローカルリポジトリの master ブランチからgit-training/#{N}-breakfast ブランチを作成しプッシュする。
   ```
    各開発担当者のpullコマンドは禁止です。fetchコマンドを使用してください。
   ```

 2. 各開発担当者は ローカルリポジトリの git-training/#{N}-breakfast ブランチをチェックアウトし、リモートリポジトリの git-training/#{N}-breakfast をプルして  `feature-{name}-{mmdd}`ブランチをローカルリポジトリに作成する。リモートリポジトリのブランチ名を`git-training/#{N}-{name}-breakfast-{mmdd}`として`feature-{name}`ブランチをプッシュする。

 3. ローカルリポジトリにて作業をコミットする。コミットメッセージは、 `ebook-okazaki/git-training#{N} 誰の朝食か（どんな修正か）` の形式にする。

 4. コミットをリモートリポジトリへプッシュし、PR を作成する。PRのタイトルは、`git-training/#{N}-{name}-breakfast-{mmdd}からgit-training/#{N}-breakfastへのマージ(git-training/#{N})` とする。

 5. PR をレビュアーへ回し、レビューしてもらう。レビュアーのアサインは ◇◇→〇〇→▽▽→◇◇ にお願いするものとする。

 6. PR のレビュアーは編集内容を確認し、間違いやコンフリクト発生などの問題がなければマージする。また、マージした作業ブランチ( git-training/#{N}-{name}-breakfast-{mmdd} )の削除を行う。問題がある場合は、編集者へその内容を報告し、修正してもらう。マージの順番は、◇◇→〇〇→▽▽の順でお願いします。
   ```
    コンフリクトの解消方法は1日目はmergeを使用、2日目はrebaseを使用して解消してください。
   ```
 1日目はここまでで終了です。2日目は2～開始してください。

 7. 全ての内容が リモートリポジトリの git-training/#{N}-breakfast へマージされた時点で、リリース担当者は リモートリポジトリの master ブランチへの PR を作成する。PR タイトルは git-training/#{N}-breakfastからmasterへのマージ(git-training/#{N}) とする。

 8. 検収担当者は内容を確認後、問題がなければマージする。また、マージした作業ブランチ( git-training/#{N}-breakfast )の削除を行う。

 9. リリース担当者はリリースタグの設定・リリース結果確認を行う。

 10. 検収担当者はリリース担当者の記録を確認し、 issue をクローズする。

## 開発時に使用する環境

 |環境|URL|
 |---|---|
 |PR環境|https://git-training-breakfast-o-pr-{N}.herokuapp.com/|
 |本番環境|https://git-training-breakfast-oka.herokuapp.com/|

 - PR時にはPR番号{N}の環境をブラウザで確認する

## 作業担当者の割り当て

 - issue作成者：◇◇
 - branch作成者：〇〇
 - 開発担当者(朝食報告、3名)：◇◇、〇〇、▽▽
 - 検収担当者：◇◇
 - リリース担当者：〇〇

## 判定基準

 - [ ] issue作成者が、issueを作成した
 - [ ] branch作成者が、issue branchを作成した
 - [ ] 開発担当者が、git-training/#{N}-breakfast ブランチへのPRを作成した
 - [ ] 開発担当者が、回ってきた git-training/#{N}-breakfast ブランチへのPRをマージ完了した
 - [ ] リリース担当者が、master branchへのPRを作成した
 - [ ] 検収担当者が、master branchへのPRをマージ完了した
 - [ ] リリース担当者が、master branchのHEADに対して、releases/tagsを設定し、issueに記載した
 - [ ] リリース担当者が、master branch がデプロイされた結果を確認し、issueに確認した結果を記載した
 検収担当者が、issueをcloseした