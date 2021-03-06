
## V佬的项目基础上更新

1.内嵌播放

2.侧边栏功能

3.增加glightbox插件，支持图片响应式弹出，滑动查看。
如希望视频也才用此插件，请修改view/nexmoe/list.php第107行视频对应的class="iframe"改为class="glightbox"

后台侧边栏代码示例
```
    <div class="mdui-collapse-item">
        <div class="mdui-collapse-item-header mdui-list-item mdui-ripple">
            <i class="mdui-list-item-icon mdui-icon material-icons">folder</i>
            <div class="mdui-list-item-content">Test</div>
            <i class="mdui-collapse-item-arrow mdui-icon material-icons">keyboard_arrow_down</i>
        </div>
        <div class="mdui-collapse-item-body mdui-list">
            <a href="/?/456" class="mdui-list-item mdui-ripple ">456</a>
        </div>
	<div class="mdui-collapse-item-body mdui-list">
            <a href="/?/345" class="mdui-list-item mdui-ripple ">345</a>
        </div>      
    </div>

    <a href="/?/234" class="mdui-list-item mdui-ripple">
        <i class="mdui-list-item-icon mdui-icon material-icons">folder</i>
        <div class="mdui-list-item-content">234</div>
    </a>
    
    <a href="#" class="mdui-list-item mdui-ripple">
        <i class="mdui-list-item-icon mdui-icon material-icons">message</i>
        <div class="mdui-list-item-content">Telegram频道</div>
    </a>
    
    <span class="mdui-list-item mdui-ripple" id="example-bottom">
        <i class="mdui-list-item-icon mdui-icon material-icons">attach_money</i>
        <div class="mdui-list-item-content">打赏</div>
    </span>
    
    <a href="#" class="mdui-list-item mdui-ripple">
        <i class="mdui-list-item-icon mdui-icon material-icons">bubble_chart</i>
        <div class="mdui-list-item-content">Blog</div>
    </a>
    
    <a href="#" class="mdui-list-item mdui-ripple">
        <i class="mdui-list-item-icon mdui-icon material-icons">info_outline</i>
       <div class="mdui-list-item-content">关于</div>
    </a>

<script>
var $$ = mdui.JQ;
$$('#example-bottom').on('click', function () {
  mdui.snackbar({
    message: '<img src="/qr.png"/>',
    position: 'top'
  });
});
</script>

```

## 预览地址  
[od.xkx.me](https://od.xkx.me/)

----------------------------------------------------------------------------------------------

# oneindex
OneDrive Directory Index

## 功能：
不用服务器空间，不走服务器流量，  

直接列onedrive目录，文件直链下载。  


## 添加 Redis 支持（Debian 8）：
```
# 安装 redis 支持
apt-get install -y redis-server php5-redis
# 重启 fcgiwrap-php 进程
bash /etc/init.d/fcgiwrap-php restart
# 后台选择 redis 模式, 并更新缓存.
```

## 创意整合
1.极大简化安装步骤。           
2.一些样式美化修改。         
3.分页模式，加快页面预览速度。创意来自[oneindex-h](https://github.com/hang666/oneindex-h)    
4.可后台自定义网站主标题,副标题。         
5.可后台自定义每页显示项目数量。          

## 重新安装
删除 oneindex/config 下的所有文件即可.                
一键安装的地址: /var/www/oneindex/config                

## change log:  
18-03-29: 更新直链获取机制、缓存机制，避免频繁访问的token失效  
18-03-29: 解决非英文编码问题  
18-03-29: 添加onedrive共享的起始目录 功能  
18-03-29: 添加rewrite的配置文件  
18-03-29: 增加sqlite模式cache支持  
18-03-29: 添加缩略图功能  
18-03-29: 添加404判断  
18-03-31: 添加console  
18-04-13: 修复特殊文件名无法下载问题  
18-04-13: 添加命令行上传功能  
18-04-16: 更新 2.0 beta  
18-04-16: 更新展示界面  
18-04-16: 响应式，支持小屏设备  
18-04-16: 图片在线预览  
18-04-16: 视频在线播放  
18-04-16: 代码在线查看（js、css、html、sh、php、java、md等）  
18-04-16: README.md 支持，解析各目录下(onedirive目录下) README.md 文件，在页面尾部展示。  
18-04-18: 音频在线播放  
18-04-18: HEAD.md 支持，在页面头部展示   
18-04-18: .password 文件夹加密  
18-05-06: 在线视频播放器替换成 Dplayer  
18-05-06: 在线视频播放支持'mp4','webm','avi','mpg', 'mpeg', 'rm', 'rmvb', 'mov', 'wmv', 'mkv', 'asf'  
18-06-01: 支持个人账号  
18-06-01: cli文件夹上传（单线程）  
18-06-01: 管理后台(后台地址:?/admin 默认密码:oneindex)  
18-06-01: 不同后缀展示设置  
18-06-01: 文件直接输出  
18-06-01: 文件上传管理（后台） 
18-06-01: 增加index.html特性   
18-06-01: 图床功能   

## 需求：
1、PHP空间，PHP 5.6+ 打开curl支持  
2、onedrive 账号 (个人、企业版或教育版/工作或学校帐户)  
3、oneindex 程序   

## 安装：
<img width="658" alt="image" src="https://raw.githubusercontent.com/0oVicero0/oneindex/files/images/install.gif">  


## 计划任务  
[可选]**推荐配置**，非必需。后台定时刷新缓存，可增加前台访问的速度  
```
# 每小时刷新一次token
0 * * * * /具体路径/php /程序具体路径/one.php token:refresh

# 每十分钟后台刷新一遍缓存
*/10 * * * * /具体路径/php /程序具体路径/one.php cache:refresh
```

## 特殊文件实现功能  
` README.md `、`HEAD.md` 、 `.password`特殊文件使用  

可以参考[https://github.com/0oVicero0/oneindex/tree/files](https://github.com/0oVicero0/oneindex/tree/files)  

**在文件夹底部添加说明:**  
>在onedrive的文件夹中添加` README.md `文件，使用markdown语法。  

**在文件夹头部添加说明:**  
>在onedrive的文件夹中添加`HEAD.md` 文件，使用markdown语法。  

**加密文件夹:**  
>在onedrive的文件夹中添加`.password`文件，填入密码，密码不能为空。  

**直接输出网页:**  
>在onedrive的文件夹中添加`index.html` 文件，程序会直接输出网页而不列目录。  
>配合 文件展示设置-直接输出 效果更佳  

## 命令行功能  
仅能在php cli模式下运行  
**清除缓存:**  
```
php one.php cache:clear
```
**刷新缓存:**  
```
php one.php cache:refresh
```
**刷新令牌:**  
```
php one.php token:refresh
```
**上传文件:**  
```
php one.php upload:file 本地文件 [onedrive文件]
```
