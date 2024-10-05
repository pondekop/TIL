## DB(データベース)とは

DB (データベース) とは、大量のデータを効率的に保存、管理、検索するためのシステム。  
スマートフォンの連絡先アプリや、ショッピングサイトの商品の情報など、日常生活でも様々な場面でデータベースが使われている。

---

## DBの仕組み

データベースは、**テーブル（表）**という形式でデータを保存する。
テーブルは、行と列からなり、行が1つのデータ（レコード）を表し、列がそのデータの種類（名前、日付など）を表します。  

※下のテーブルでいうと、`sqlite3 mydatabase.db`、「データベースの作成・接続」が行で、「コマンド」「操作」が列。  
　漢字の横(行)と縦(列)で覚えると◎

---

## よく使われるコマンド一覧

| **コマンド**                                                                 | **操作**                   |
|------------------------------------------------------------------------------|----------------------------|
| `sqlite3 mydatabase.db`                                                       | **データベースの作成・接続** |
| `rm mydatabase.db`                                                           | **データベースの削除**      |
| `CREATE TABLE tablename (column1 datatype, column2 datatype, column3 datatype);` | **テーブルの作成**          |
| `DROP TABLE tablename;`                                                      | **テーブルの削除**          |
| `PRAGMA table_info(tablename);`                                              | **テーブルの構造を確認**    |
| `INSERT INTO tablename (column1, column2) VALUES (value1, value2);`           | **データの挿入**            |
| `UPDATE tablename SET column1 = new_value WHERE condition;`                   | **データの更新**            |
| `DELETE FROM tablename WHERE condition;`                                      | **データの削除**            |
| `SELECT * FROM tablename;`                                                   | **データの取得**            |
| `SELECT * FROM tablename WHERE condition;`                                   | **条件付きデータ取得**      |
| `SELECT * FROM tablename ORDER BY column_name ASC;` または `DESC;`            | **昇順・降順でソート**      |
| `SELECT * FROM tablename LIMIT 10;`                                          | **データの取得行数制限**    |
| `ALTER TABLE tablename ADD COLUMN new_column datatype;`                       | **列の追加**                |
| `DROP TABLE tablename;`                                                       | **列の削除**（手動で実施）  |
| `CREATE INDEX index_name ON tablename (column_name);`                         | **インデックスの作成**      |
| `DROP INDEX index_name;`                                                     | **インデックスの削除**      |

---

## トランザクション操作

### トランザクションの開始・コミット・ロールバック

トランザクションは、一連のデータベース操作をまとめて実行し、その間にエラーが発生した場合はすべての操作を元に戻すこと（ロールバック）ができる機能。  
事前にBEGINをしておけば、間違えて消したくないデータやテーブルを消してしまった場合もROLLBACKで取り消すことができる。

```sql
-- トランザクションを開始
BEGIN TRANSACTION;

-- 一連の操作を実行
INSERT INTO tablename (column1, column2) VALUES (value1, value2);
UPDATE tablename SET column1 = new_value WHERE condition;

-- トランザクションをコミット（確定）
COMMIT;

-- エラーが発生した場合はロールバック（変更を取り消す）
ROLLBACK;
```
