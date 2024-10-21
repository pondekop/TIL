 .venv\Scripts\activate でアクティベートしたあと  
FLASK_APP=app  
FLASK_ENV=development の後に
flask runをすると
```
* Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:5000
Press CTRL+C to quit
```
と出てくるが、これは*「開発サーバーであり、実稼働環境では使用しないでください」*といった内容の警告メッセージで、プログラム上の仕様なので問題なし。
この場合、http://127.0.0.1:5000がローカル環境のホスト。

---

変更が即時更新されない場合、
```
flask run --debug
```
でデバッグモードをオンにすることで変更を即時反映することができる。

---

```
@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
```
ここのWorldに入る文字列(XX)をURLの末尾から自動で`Hello, XX!`として返すようにしたい

```
@app.route("/<name>")
def hello(name):
    return "<p>Hello, { name }!</p>"
```
これによってURLの末尾を変えることで自動で表示される名前が変わる

---
`sha256`はエラーが起きるので`pbkdf2:sha256`と入力する
