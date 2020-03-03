## Introduce

### 1. Flask: 輕量級 Web 應用框架
詳細說明請參考 [Flask Documentation](https://flask.palletsprojects.com/)  
首頁的圖案是角型容器不是辣椒

### 2. 最小的 Flask 程式
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
	return "Hello Flask!"
```

### 3. 如何在本機執行
加入下列段落後運行程式，使用瀏覽器開啟 [http://localhost:5000](http://localhost:5000)
```python
if __name__ == '__main__':
    app.run(host='0.0.0.0')
```

<br/><br/><br/>

[[回到Flask文章列表]](index.md)  
