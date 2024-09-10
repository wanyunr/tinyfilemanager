# Tiny File Manager
[![GitHub License](https://img.shields.io/github/license/prasathmani/tinyfilemanager.svg?style=flat-square)](https://github.com/wanyunr/tinyfilemanager/blob/master/LICENSE) [![tinyfilemanager](https://img.shields.io/badge/Powered-tinyfilemanager-green)](https://github.com/prasathmani/tinyfilemanager)  [![](https://img.shields.io/badge/Source-Github-%232196f3)](https://github.com/wanyunr/tinyfilemanager)

## PHP环境部署

```bash
wget https://gitee.com/wanyunr/tinyfilemanager/repository/archive/main.zip  # 下载文件到网站根目录
unzip main.zip #解压文件
mv tinyfilemanager-main/* .  #移出文件到根目录
mv tinyfilemanager.php index.php  #重命名文件
rm -r tinyfilemanager-main && rm main.zip #删除多余文件
```

## Docker 部署

```bash
docker run -d \
    -v /absolute/path:/var/www/html/data \
    -p 3380:3380 --restart=always \
    --name tinyfilemanager-2.5.3 \
 ccr.ccs.tencentyun.com/txre/tinyfilemanager:tag-v2.5.3
```

#### 如何在Docker中更改配置

下载 `tinyfilemanager.php`并更名为`index.php`，根据需要更改配置，并在命令中添加一个新卷，如下所示：`-v /absolute/path/index.php:/var/www/html/index.php`

 ```bash
docker run -d \
    -v /absolute/path:/var/www/html/data \
    -v /absolute/path/index.php:/var/www/html/index.php \
    -p 3380:3380 \
    --restart=always \
    --name tinyfilemanager \
ccr.ccs.tencentyun.com/txre/tinyfilemanager:tag-v2.5.3
 ```
更多配置请参考 [Tiny File Manager Wiki](https://github.com/prasathmani/tinyfilemanager/wiki/Config-Flags)

### 构建自己镜像

```bash
#下载文件
wget https://gitee.com/wanyunr/tinyfilemanager/repository/archive/main.zip
#解压
unzip main.zip
cd tinyfilemanager-main
# 根据需要修改 tinyfilemanager.php 的内容
# 构建镜像，以2.5.3为例（注意后面有个点）
docker build -t tinyfilemanager:2.5.3 . 
#运行镜像
docker run -d -v /absolute/path:/var/www/html/data -p 3380:3380 --restart=always --name tinyfilemanager-2.5.3 tinyfilemanager:2.5.3
```


## 修改内容

- 修改CDN为 [字节跳动静态资源公共库](https://cdn.bytedance.com)
- 隐藏`translation.json`文件
- 推荐可用的[在线PHP密码生成器](https://uutool.cn/php-password)