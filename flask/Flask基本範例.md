## Flask 基本範例

### 最小的 Flask 程式
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
	return '<h1>Hello Flask!</h1>'
```

### 綁定多個 URL
```python
@app.route('/hi')
@app.route('/hello')
def say_hello():
	return '<h1>Hello Flask!</h1>'
```

### 從 URL 傳參數
```python
@app.route('/greet')
@app.route('/greet/<name>')
def greet(name='Guest'):
	return '<h1>Hello, %s!</h1>' % name
```
> 在本例中我們將 name 預設為 Guest，避免 URL 沒有帶參數的情形。





[回到Blog首頁](../index.md)
