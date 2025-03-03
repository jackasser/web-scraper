# ウェブスクレイパー - GitHub Actions版

このリポジトリは、GitHub Actions を利用して特定のウェブサイトとその配下のページを一括取得するスクレイピングツールです。スクレイピング結果はGitHub Pagesで閲覧できます。

## 特徴

- **無料**: GitHub Actionsの無料枠で実行可能
- **簡単な設定**: ブラウザから直接実行可能（コマンドラインやローカル環境不要）
- **カスタマイズ可能**: 深度、ファイルタイプ、除外パターンなどを指定可能
- **自動UI生成**: スクレイピング結果を閲覧するための検索可能なWebインターフェース
- **GitHub Pagesデプロイ**: 結果をWebで閲覧・共有可能

## 使い方

### 1. リポジトリをフォーク

このリポジトリをフォークして、自分のGitHubアカウントにコピーします。

### 2. GitHub Pagesを有効化

1. リポジトリ設定 > Pages を開く
2. ソースに「gh-pages」ブランチを選択
3. 「保存」をクリック

### 3. スクレイピングの実行

1. リポジトリの「Actions」タブを開く
2. 「Web Scraper」ワークフローを選択
3. 「Run workflow」ボタンをクリック
4. 以下のパラメータを入力:
   - `target_url`: スクレイピング対象のURL (例: https://example.com)
   - `max_depth`: クロールする深さ (推奨: 1-5)
   - `file_types`: 取得するファイル形式 (カンマ区切り、例: html,pdf,jpg)
   - `exclude_patterns`: 除外するURLパターン (カンマ区切り、例: /blog/,/author/)
5. 「Run workflow」をクリック

### 4. 結果の確認

スクレイピングが完了すると、GitHub Pagesで結果を確認できます。
URL: `https://[あなたのユーザー名].github.io/[リポジトリ名]/`

## 重要な注意事項

- **利用規約を遵守**: スクレイピングするウェブサイトの利用規約を確認し、許可されていることを確認してください
- **負荷に配慮**: 過度なリクエストでサーバーに負荷をかけないようにしてください
- **プライバシー**: 個人情報などセンシティブな情報のスクレイピングは避けてください
- **著作権**: 取得したコンテンツの著作権に注意してください
- **robots.txt**: サイトのrobots.txtを確認し、クロールが許可されていることを確認してください

## GitHub Actions使用制限

無料アカウントでは以下の制限があります:
- 月2,000分のGitHub Actions実行時間
- スクレイピングが大規模になると制限に達する可能性があります
- 60分以上実行できないジョブ実行時間制限があります

## カスタマイズ

より高度なカスタマイズが必要な場合は、以下のファイルを編集してください:
- `scraper.py`: スクレイピングロジック
- `create_ui.py`: UI生成ロジック
- `.github/workflows/scrape.yml`: GitHub Actionsワークフロー設定

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。
