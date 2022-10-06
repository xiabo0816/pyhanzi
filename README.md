# pyhanzi


# pyhanzi功能

- [ ] 简繁转换

- [ ] 字形相似

- [ ] 偏旁部首

- [ ] 分句

- [ ] 最大长度匹配分词

- [ ] 正则表达式封装

- [ ] 各种主题字表

- [ ] 汉字字典

- [ ] 全角半角转换

- [ ] 清空html属性

- [ ] 提取html正文

- [ ] 生成文件名

- [ ] 各领域的停用词

- [ ] 标题中的停用词


## 发布

```bash
python3 -m venv pyhanzi-venv/
source pyhanzi-venv/bin/activate.fish

# 调试好之后
python3 -m pip install --upgrade pip -i https://mirrors.aliyun.com/pypi/simple/
pip3 install -i https://mirrors.aliyun.com/pypi/simple/ setuptools wheel
python3 setup.py sdist bdist_wheel

pip3 freeze > requirements.txt
# requirements添加一个peppercorn
echo 'peppercorn' >> requirements.txt
pip3 download -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple/ -d dist/

cd dist/
dir2pi -S .
scp -r simple/ root@39.97.232.223:/root/pypi/
pip3 install -i http://www.hohohaha.cn:8000/simple/ pyhanzi==0.0.2 --trusted-host www.hohohaha.cn
```

## 上传到pypi

```bash
# python3 -m venv pyhanzi-venv/
source pyhanzi-venv/bin/activate.fish
rm -rf dist/*
python3 setup.py sdist bdist_wheel
pip3 install -i https://mirrors.aliyun.com/pypi/simple/ twine
python3 -m twine upload dist/*
```

## 安装

```bash
pip3 install -i https://pypi.python.org/simple pyhanzi
```

# 开发配置

