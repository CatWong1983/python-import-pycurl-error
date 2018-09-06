# python-import-pycurl-error
**在python中import pycurl的时候有时候会报错
  ImportError: pycurl: libcurl link-time ssl backend (openssl) is different from compile**
  
可以通过重新安装来解决
但是这里就会有个坑，在高版本的mac系统环境变量里是找不到openssl的头文件的
不多说直接上命令行
```
pip uninstall pycurl
export PYCURL_SSL_LIBRARY=openssl
export LDFLAGS=-L/usr/local/opt/openssl/lib
export CPPFLAGS=-I/usr/local/opt/openssl/include
pip install pycurl --compile --no-cache-dir
```
