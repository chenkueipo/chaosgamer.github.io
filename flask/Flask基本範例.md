## Flask基本範例

### 最小的Flask程式
```c
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
	return '<h1>Hello Flask!</h1>'
```


[回到Blog首頁](../index.md)
