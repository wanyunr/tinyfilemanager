# Tiny File Manager
[![GitHub License](https://img.shields.io/github/license/prasathmani/tinyfilemanager.svg?style=flat-square)](https://github.com/wanyunr/tinyfilemanager/blob/master/LICENSE) [![tinyfilemanager](https://img.shields.io/badge/tinyfilemanager-Powered-green)](https://github.com/prasathmani/tinyfilemanager)

## PHP环境部署

```bash
wget https://github.com/wanyunr/tinyfilemanager/archive/refs/heads/dev.zip  # 下载文件到网站根目录
unzip dev.zip #解压文件
mv tinyfilemanager-dev/* .
rm -r tinyfilemanager-dev && rm dev.zip #删除多余文件
```

## Docker部署

```
#下载文件
wget https://github.com/wanyunr/tinyfilemanager/archive/refs/heads/dev.zip
#解压
unzip dev.zip
cd tinyfilemanager-dev
mv index.php tinyfilemanager.php
# 根据需要修改index.php的内容
# 构建镜像，以2.5.3为例（注意后面有个点）
docker build -t tinyfilemanager:2.5.3 . 
#运行镜像
docker run -d -v /absolute/path:/var/www/html/data -p 3380:3380 --restart=always --name tinyfilemanager-2.5.3 tinyfilemanager:2.5.3
```


## 修改内容

- 修改CDN源为Bootcdn等
- 隐藏`index.php`和`translation.json`文件
- 推荐可用的在线PHP密码生成器

