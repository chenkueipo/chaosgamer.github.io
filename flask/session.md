## Session

### 1. 設置密鑰
透過 os.urandom 函數隨機產生 12 bytes 的字串做為密鑰
```python
from flask import Flask
import os

app = Flask(__name__)
app.config.update(dict(
    SECRET_KEY = os.urandom(12)
))
```

### 2-1. 模擬用戶登入 (設定Session變數)
用戶拜訪 /login 頁面後儲存 'logged_in' 變數至 session，並重新導向至歡迎頁面。
```python
from flask import Flask, session, redirect, url_for
app = Flask(__name__)

@app.route('/login')
def login():
    session['logged_in'] = True
    return redirect(url_for('hello'))
```

### 2-2. 模擬登出用戶 (移除Session變數)
用戶拜訪 /logout 頁面後移除 session 的'logged_in' 變數，並重新導向至結束頁面。
```python
from flask import Flask, session, redirect, url_for
app = Flask(__name__)

@app.route('/logout')
def logout():
    if 'logged_in' in session:
        session.pop('logged_in')
    return redirect(url_for('goodbye'))
```

<br/><br/><br/>

[[回到Flask文章列表]](index.md)  
