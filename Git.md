## Gitとは？

Gitは、ソースコードやファイルのバージョン管理を行う分散型バージョン管理システム。  
複数の開発者が共同で開発を行う際、変更履歴を記録・追跡し、変更点を統合するために使用される。

### 主な特徴
- **履歴管理**：ファイルの変更履歴(バージョン)を保存し、過去の変更箇所を確認したり、バージョンに戻したりすることができる。
- **分散型**：各開発者がローカルでリポジトリを持ち、インターネット接続がなくても作業できる。複数人で進めた開発を集約することができる。
- **ブランチ管理**：異なる機能や修正を並行して開発でき、後で統合することが可能。

※分散型の他に「集中型」があり、「集中型」の場合はサーバー上の特定のリポジトリに接続しておく必要がある。そのため、オフラインの状態ではリポジトリの反映などはできない。

---

## よく使われるコマンド一覧

| コマンド        | 説明                                      |
|-----------------|-------------------------------------------|
| `git init`      | リポジトリの作成                          |
| `git clone`     | リポジトリのコピー                        |
| `git pull`      | リモートリポジトリの変更を取り込む        |
| `git add`       | ファイルをインデックスに追加              |
| `git commit`    | ファイルをコミット                        |
| `git push`      | リモートリポジトリに変更を反映            |
| `git branch`    | ブランチの作成・一覧表示                  |
| `git checkout`  | ブランチの切り替え                        |
| `git merge`     | 現在のブランチを他のブランチとマージする  |
| `git rebase`    | 元のブランチに変更点をマージ              |