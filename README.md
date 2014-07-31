EgretWeixinJSBridge
===================
本项目是 Egret 的非官方扩展 - 微信 JavaScript Bridge 接口

本项目的JavaScript源代码来源于 [这里](https://github.com/zxlie/WeixinApi) ，本项目未修改其源代码，只是将其添加了 .d.ts 描述文件，并调整为 egret 第三方组件库的标准结构。感谢原作者的辛勤劳动！


使用方法
--------------

在 Egret 的下个版本中会提供自动化的模块添加机制，但如果开发者现在就有需求使用此模块，请按照以下方式添加到游戏中



* 复制 ``` bin/WeixinAPI.js ``` 到 游戏项目中的 ``` launcher/WeixinAPI.js ```
* 复制 ``` libs/WeixinAPI.d.ts ``` 到 游戏项目中的 ``` libs/WeixinAPI.d.ts ```
* 在游戏项目的 ``` index.html ``` 中添加 ``` <script src="launcher/WeixinAPI.js" async="false"></script> ```
* 参考 GameApp.ts 中的调用方式，实现开发者的分享需求


```

   //  当游戏结束，开发者引导用户去分享时调用此代码

  WeixinApi.ready(function(api:WeixinApi){

            alert("WeixinAPI Ready!!");

            var info:WeixinShareInfo = new WeixinShareInfo();
            info.title = "HelloEgret";
            info.desc = "欢迎使用Egret";
            info.link = "www.egret-labs.org";
//                        info.imageUrl = "";


            api.shareToFriend(info);
            api.shareToTimeline(info);
        })




```
