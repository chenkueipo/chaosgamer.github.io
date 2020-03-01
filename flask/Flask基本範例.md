## Flask基本範例

### 最小的Flask程式
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
	return '<h1>Hello Flask!</h1>'
```

### 綁定多個URL
```python
@app.route('/hi')
@app.route('/hello')
def index():
	return '<h1>Hello Flask!</h1>'
```

### 從URL傳參數
```python
@app.route('/greet/<name>')
def index():
	return '<h1>Hello, %s!</h1>' % name
```

[回到Blog首頁](../index.md)
