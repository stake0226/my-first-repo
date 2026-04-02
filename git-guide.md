# Git & GitHub 入門ガイド

## Gitとは？

RPGゲームの「セーブ機能」と同じです。

- コードを書く = ゲームを進める
- `git commit` = セーブする
- 過去に戻りたい = セーブデータをロードする

## GitHubとは？

セーブデータをクラウドに保存するイメージです。

- ローカル（自分のPC） = 本体のセーブデータ
- GitHub = クラウドのバックアップ
- `git push` = クラウドに同期する

---

## 初期設定（最初に1回だけやること）

### 1. Gitのインストール確認
```
git --version
```
バージョンが表示されればOK。

### 2. GitにGitHubのアカウント情報を登録
```
git config --global user.name "GitHubのユーザー名"
git config --global user.email "GitHubに登録したメールアドレス"
```

### 3. 確認
```
git config --global user.name
```
ユーザー名が表示されればOK。

### 4. GitHub CLIのインストール
```
winget install --id GitHub.Cli
```

### 5. GitHubと認証連携
```
gh auth login
```
- `GitHub.com` を選択
- `HTTPS` を選択
- `Y` を選択
- `Login with a web browser` を選択
- 表示されたコードをブラウザで入力してログイン

---

## 新しいリポジトリを作る手順

```
cd ~
mkdir プロジェクト名
cd プロジェクト名
git init
echo "# プロジェクト名" > README.md
git add README.md
git commit -m "first commit"
gh repo create プロジェクト名 --public --source=. --push
```

---

## 毎日の使い方（これだけ覚えればOK）

```
# ファイルを編集したら
git add ファイル名
git commit -m "何をしたか一言で"
git push
```

---

## Claude Code（ターミナル版）との連携

Claude Codeを使うと自然言語でGit操作を指示できます。

- 「このファイルを修正してコミットして」
- 「コミットメッセージを考えて」
- 「GitHubにプッシュして」

---

## Claude CodeとClaude Desktopの違い

| | Claude Code（ターミナル版） | Claude Desktop |
|--|--|--|
| 用途 | コード作業・Git操作 | 会話・相談 |
| Git操作 | 直接実行できる | 基本的にできない |
| 会話履歴 | 残らない | 残る |

---

## まとめ

- **Git** = ローカルのセーブ機能
- **GitHub** = クラウドのバックアップ
- **git add** = セーブ対象を選ぶ
- **git commit** = セーブする
- **git push** = クラウドに同期する
