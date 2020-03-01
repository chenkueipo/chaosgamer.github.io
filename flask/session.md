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

<br/><br/><br/>

[回到Blog首頁](../index.md)

<br/>
