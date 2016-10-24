# git-practice
朝食と昼食まとめ用リポジトリ

[朝食リポジトリ](https://github.com/matsuo-y/git-practice-breakfast)
[昼食リポジトリ](https://github.com/matsuo-y/git-practice-lunch)

issue用ブランチはstagingから切る

#10/24まで
- 朝食・昼食ともにmasterまでマージ

#10/25～

## 朝食リポジトリ
`アプリ内書店の開発のように、リリースまでの開発期間が長いブランチ戦略`
- 報告担当2人
- issue用ブランチへのマージまで行う
- staging,masterへのマージは行わない

## 昼食リポジトリ
`開発内容を即時リリースするように、リリースまでの開発期間が短いブランチ戦略`
- 報告担当1人
- レビュー担当者は、issue用ブランチへのプルリクマージ前に最低1度レビューで修正依頼を出す
- staging,masterへのマージまで行う
