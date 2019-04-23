原项目出自一个大佬的博客，猫与向日葵。[阅读原文](https://imjad.cn/archives/lab/add-dynamic-poster-girl-with-live2d-to-your-blog-02 "阅读原文")  
本文对于原文和原作有删改。  

WordPress插件版安装即可使用，不用手动添加代码 (推荐使用)  原作者[@daidr](https://daidr.me "@daidr")

原模型来自手游[药水制作师];
洛天依模型是我通过贴图修改制作的，流下了不会画画的泪水。。。。

增加了播放音乐的功能；
因为只有一个模型，暂时隐藏了换装功能
详细信息请看我的博客[阅读原文](https://unsignedzhang.cn/luotianyi-live2d/ "阅读原文")  

可以访问我的主页或 https://unsignedzhang.cn/live2d.html 查看演示

### 正式开工
在你博客程序头部文件（header）引入界面样式，在 head 标签内插入如下代码：
```html
<link rel="stylesheet" href="/live2d/css/live2d.css" />
```

在 body 标签内合适的位置插入 Live2D 看板娘的元素，按照 Html 书写规范写 ~
```html
<div id="landlord">
    <div class="message" style="opacity:0"></div>
    <canvas id="live2d" width="280" height="250" class="live2d"></canvas>
    <div class="hide-button">隐藏</div>
</div>
```

在你博客程序页脚文件（footer）引入脚本，在 body 标签结束前插入如下代码：
```html
<script type="text/javascript">
    var message_Path = '/live2d/'
    var home_Path = 'https://localhost/'  //此处修改为你的域名，必须带斜杠
</script>
<script type="text/javascript" src="/live2d/js/live2d.js"></script>
<script type="text/javascript" src="/live2d/js/message.js"></script>
<script type="text/javascript">
    loadlive2d("live2d", "/live2d/model/tia/model.json");
</script>
```

鼠标放在页面某个元素上时，需要 Live2D 看板娘提示的请修改 message.json 文件。

**示例：**
```json
{
    "mouseover": [
        {
            "selector": ".title a",  //此处修改为你页面元素的标签名
            "text": ["要看看 {text} 么？"]  //此处修改为你需要提示的文字
        },
        {
            "selector": "#searchbox",
            "text": ["在找什么东西呢，需要帮忙吗？"]
        }
    ],
    "click": [  //此处是 Live2D 看板娘的触摸事件提示
        {
            "selector": "#landlord #live2d",
            "text": ["不要动手动脚的！快把手拿开~~", "真…真的是不知羞耻！","Hentai！", "再摸的话我可要报警了！⌇●﹏●⌇", "110吗，这里有个变态一直在摸我(ó﹏ò｡)"]
        }
    ]
}
```

然后，刷新你的博客页面，看看效果吧！

注意路径别弄错了噢 ~  
PHP 程序推荐使用主题函数获取绝对路径。

**问：“为什么这个 Live2D 没有换装功能哎？”**  
**答：“自己研究去。”**
  
~~其实，就是动态改变 model.json 内的服装字段，达到随机服装的效果……~~

**问：“怎么添加或修改歌曲？”**  
**答：“修改songs.json文件即可。”**


### 模型欣赏
![](https://unsignedzhang.cn/wp-content/uploads/20190423161907.png)
![](https://unsignedzhang.cn/wp-content/uploads/20190423161719.png)

### 模型说明
> Live2D 并不是一种先进的技术，它产生的效果，都是用基本的平移、旋转、透明、曲面变形等操作实现的。
最终的效果与贴图关系很大，而每一个动作，都需要制作师的精细调整。
这是一个需要消耗大量时间精力的过程，因此质量好的模型并不多，质量好的也一般是在游戏中，版权受到保护，**不能随意使用**。

原模型解包自 [药水制作师](https://play.google.com/store/apps/details?id=com.sinsiroad.potionmaker&hl=zh_CN "药水制作师") 手机游戏，版权归该官方所有。




