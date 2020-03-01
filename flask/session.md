## Session: 儲存用戶訊息

### 設置密鑰
透過 os.urandom 函數隨機產生 12 bytes 的字串做為密鑰
```python
from flask import Flask
import os

app = Flask(__name__)
app.config.update(dict(
    SECRET_KEY = os.urandom(12)
))
```

<br/>

### 模擬用戶登入
用戶拜訪 /login 頁面後儲存登入紀錄至 session ，並轉址至歡迎頁面。
```python
from flask import Flask, session, redirect, url_for
app = Flask(__name__)

@app.route('/login')
def login():
    session['logged_in'] = True
    return redirect(url_for('hello'))
```

<br/>

### 模擬登出用戶
用戶拜訪 /logout 頁面後清空 session 的登入紀錄，並轉址至結束頁面。
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

[回到Blog首頁](../index.md)

<br/>
