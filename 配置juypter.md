
# 配置jupyter,可视化python
pip install jupyter
## 设置更目录 /home/chan87/biosoft/jupyter/root，就是创建文件
## 输入配置文件命令
jupyter notebook --generate-config
## 确认转码的密码，并记录argon2:$argon2id$v=19$m=10240,t=10,p=8$CUdkf+2S+T8n3FuOsxejfA$tTNH9D587i5+FyGMzrrnDG9PhrCMf58TRCZg9KteZTo，这个是我的简约密码
### 打开python3
```python
from notebook.auth import passwd
passwd()
```
## 进入~/.jupyter，配置jupyter_notebook_config.py，输入以下内容
```linux
# 允许root的管理员运行
c.NotebookApp.allow_root = True
# 设置ip
c.NotebookApp.ip = '127.0.0.1'
# 禁止打开浏览器
c.NotebookApp.open_browser = False
# 输入密匙
c.NotebookApp.password = "argon2:$argon2id$v=19$m=10240,t=10,p=8$CUdkf+2S+T8n3FuOsxejfA$tTNH9D587i5+FyGMzrrnDG9PhrCMf58TRCZg9KteZTo"
# 设置端口
c.NotebookApp.port = 8888
# 设置根目录
c.ContentsManager.root_dir = '/home/chan87/biosoft/jupyter/root'
c.NotebookApp.allow_origin = '*'
```
# 打开端口，并切查看nohup.out的端口
nohup jupyter notebook --ip 0.0.0.0 &

# 添加conda环境
## 添加conda环境到jupyter
python -m ipykernel install --user --name velocyto --display-name "python velocyto"
