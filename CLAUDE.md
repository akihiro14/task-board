# task-board

## プロジェクト概要

Reactで作成したタスク管理ボードアプリケーション。

## デプロイ先

https://akihiro14.github.io/task-board/ ✅ 公開済み（2026-06-02）

## 技術スタック

| カテゴリ | 技術 | バージョン |
|---|---|---|
| UIライブラリ | React | 19 |
| ビルドツール | Vite | 8 |
| 言語 | JavaScript (JSX) | ES2022+ |
| スタイリング | CSS (vanilla) | - |
| 永続化 | localStorage | ブラウザ標準 |
| デプロイ | GitHub Actions | - |

## ディレクトリ構成

```
task-board/
├── src/
│   ├── App.jsx       # メインコンポーネント（タスク追加・完了・削除）
│   ├── App.css       # アプリ全体のスタイル
│   ├── index.css     # ベーススタイル（リセット）
│   └── main.jsx      # エントリーポイント
├── index.html
├── vite.config.js
└── package.json
```

## 機能

- テキスト入力でタスクを追加（Enter キーまたは追加ボタン）
- チェックボックスで完了・未完了を切り替え
- タスクを削除
- 完了済みのタスクはグレー・打ち消し線で表示
- ローカルストレージによるタスクの永続化

## コンポーネント命名規約

- **ファイル名**: PascalCase（例: `App.jsx`, `TaskItem.jsx`）
- **コンポーネント関数名**: ファイル名と同じ PascalCase
- **CSS クラス名**: kebab-case（例: `.task-list`, `.input-row`）
- **イベントハンドラ**: `handle` プレフィックス（例: `handleKeyDown`）
- **状態操作関数**: 動詞 + 対象（例: `addTask`, `toggleTask`, `deleteTask`）
- **state 変数**: camelCase の名詞（例: `tasks`, `input`）

## 開発コマンド

```bash
npm install      # 依存関係のインストール
npm run dev      # 開発サーバー起動 (http://localhost:5173)
npm run build    # プロダクションビルド
```

## GitHub Pages

- URL: https://akihiro14.github.io/task-board/
- `vite.config.js` の `base: '/task-board/'` でサブパスに対応
- `main` ブランチへプッシュすると GitHub Actions が自動でビルド＆デプロイ（`.github/workflows/deploy.yml`）
- 初回のみ: GitHubリポジトリの Settings → Pages → Source を `gh-pages` ブランチに設定すること

## Git 運用ルール

- コードを変更するたびに GitHub へプッシュする
- コミットメッセージは変更内容を日本語で簡潔に記述する
- 例: `git add -A && git commit -m "機能追加: タスクの追加機能を実装" && git push`
- main ブランチへ直接プッシュする（学習目的のため）

## コーディング規約

- コメントは原則書かない（命名で意図を表現する）
- セキュリティ上の問題（XSS、SQLインジェクション等）は即座に修正する
- 不要な抽象化・先読み実装はしない
