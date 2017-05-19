##  用途

用于采集网上的公用代理IP,目前该程序仍在跑，每隔三小时刷新一遍代理IP，并将可用代理IP 上传到七牛云，可用性测试用的百度，不保证其他网站代理可用。

想直接获取可用代理IP 的可以直接使用[这个](http://7xrnwq.com1.z0.glb.clouddn.com/proxy_list.txt?v=100)

因为七牛CDN的原因，可能存在源文件已更新，但命中缓存仍然是之前没变的文件，这时，可以在这个 url “http://7xrnwq.com1.z0.glb.clouddn.com/proxy_list.txt” 后面添加“?v=2000” ，比如“http://7xrnwq.com1.z0.glb.clouddn.com/proxy_list.txt?v=2000” 数字可以随意，尽量大，即可获取最新的文件。
## 说明

#### config.py

相关配置文件，比如代理网站站点，代理IP 输出位置，超时时间等，详情见注释。

#### proxyspider.py

主程序，大致包括一个用于采集网上代理IP 的线程，多个用于测试代理IP 是否可用的线程，测试网站用的百度，详情见注释。

#### proxy_list.txt

最终代理IP 的输出文档。

#### qiniuupload.py

将proxy_list.txt，定期提交到七牛云存储，目前是维护在这里[链接] (http://7xrnwq.com1.z0.glb.clouddn.com/proxy_list.txt)

如果要用此模块的话，需要先安装七牛的库，pip install qiniu


## 使用

git clone https://github.com/zhangchenchen/proxyspider.git

cd proxyspider

python proxyspider.py

