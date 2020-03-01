## Flask 基本範例

### 最小的 Flask 程式
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
	return 'Hello Flask!'
```


### 綁定多個 URL
在本例中我們將 say_hello() 同時註冊兩個路由
```python
@app.route('/hi')
@app.route('/hello')
def say_hello():
	return 'Hello Flask!'
```


### 從 URL 傳參數
在本例中我們將 name 預設為 Guest，避免 URL 沒有帶參數的情形。
```python
@app.route('/greet')
@app.route('/greet/<name>')
def say_hello(name='Guest'):
	return 'Hello, %s!' % name
```


### redirect() + url_for() 
透過重新導向的方式，讓相同的路由設定不重覆出現。  
在本例中 url_for('greet', name='Guest') = "/hello/Guest"
```python
@app.route('/hello/<name>')
def greet(name):
    return 'Hello, %s!' % name

@app.route('/')
def index():
	return redirect(url_for('greet', name='Guest'))
```



[回到Blog首頁](../index.md)
<br/>
