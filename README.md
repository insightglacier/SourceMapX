# SourceMapX

### 批量扫描并恢复sourcemap的源代码文件。

## 安装

该脚本主要由[unwebpack-sourcemap](https://github.com/rarecoil/unwebpack-sourcemap)项目修改而来，使用Python3编写,需要安装 `BeautifulSoup4` and `requests`.可以使用 `pip3 install -r requirements.txt`命令进行安装。主要是修改为批量检测并下载，可用于SRC的漏洞挖掘。

## 使用

命令参数：
```
usage: SourceMapX.py [-h] [-m METHOD] [-d] [-o OUTPUT] uri_or_file

A tool to extract code from Webpack sourcemaps. Turns black boxes into gray ones.

positional arguments:
  uri_or_file           The target URI or file.

optional arguments:
  -h, --help            show this help message and exit
  -m METHOD, --method METHOD
                        L:Local, R:Remote
  -d, --detect          Attempt to detect sourcemaps from JS assets in retrieved HTML.
  -o OUTPUT, --output OUTPUT
                        Make the output directory if it doesn't exist.

```
其中-m有R和L，R为Remote（远程），L为Local（本地）。

-o 为结果文件保存的路径。默认为output。

将要扫描的url存放到文件中（需要带http或https），如urls.txt，然后运行如下命令。

```
python SourceMapX.py -m R -d urls.txt
```

对于探测到的.map文件会url地址会保存到`results.txt`文件中。

程序还不够完善，后续看情况是否更新吧。

Happy Hacking!!!

## 致谢

[unwebpack-sourcemap](https://github.com/rarecoil/unwebpack-sourcemap) @rarecoil

**注：请不要将该脚本用于非法用途，仅用于合法的，经过授权的渗透测试，公司内部安全检查与研究使用。由于使用工具带来的不良后果与本人无关。**
