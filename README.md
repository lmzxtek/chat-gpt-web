# ChatGPT-website(纯前端版)

## 介绍

简易版 `ChatGPT` 网站，拿来即用，适合小白，让你十分钟搭建属于自己的 `ChatGPT` 问答机器人！


## 使用说明

1. 本项目是我的`ChatGPT-website`纯前端版本，可以使用`gitee pages`或者 `github pages`零成本快速部署！

2.  本项目使用`GPT-3.5-turbo`,支持记录上下文实现连续对话！

3.  本项目支持流式响应，`markdown`实时转换为`html`！

4.  由于`openai`的`api`地区限制问题，本项目使用现成开源api代理。

5.  使用现有开源`api`代理，则只需在`config.js`文件中加入自己的 `openai` 的`api key`即可，然后使用`gitee pages`或者 `github pages`部署就行！
当然，不能将`apikey`暴露在仓库中，`github`目前会识别，然后会给你发邮件，这个`apikey`会失效，则需要重新生成。下面我会给出解决方案！


## 防止 github 识别 apiKey 解决方案

本人提供了一种方案，你在`config.js`文件中加入自己的 `openai` 的`api key`时需要加入的是`Base64`编码后的`apikey`，我在相应代码中会自动读取`config.js`中的默认`Base64`编码后的`apikey`，然后解码使用！

`Base64`编码以及解码：

`Python` ：
```
import base64

# 编码
data = 'hello world'
encoded_data = base64.b64encode(data.encode('utf-8')).decode('utf-8')
print(encoded_data)  # 输出: aGVsbG8gd29ybGQ=

# 解码
decoded_data = base64.b64decode(encoded_data).decode('utf-8')
print(decoded_data)  # 输出: hello world
```
`javascript` ：

```
// 编码
let data = 'hello world';
let encodedData = btoa(data);
console.log(encodedData);  // 输出: aGVsbG8gd29ybGQ=

// 解码
let decodedData = atob(encodedData);
console.log(decodedData);  // 输出: hello world
```

你也可以自定义加密解密规则，当然无论是否加密，我都不建议在custom.js文件中填写apiKey，有心之人防不住，容易泄露！
这只是为了防止github识别的方案，建议直接部署后在首页填入自己的apiKey使用。
如需对外提供服务，请使用项目后端版本（后端版本为flask项目，也可借助某些云平台也可实现零成本部署），因为此项目前端版本为纯静态，对外开放按上述方案依旧会使得Key泄露，且请求 `openai` 接口是用户本地浏览器发送的，只能使用代理 `api`。
感兴趣的可贡献node后端，使用Vercel也可更好的零成本部署。
总之纯前端版本流式响应效果不好，需要速度快点的建议使用后端版本或者用 Vercel 代替 github pages!

## 23 年 5.12 日更新

 1. 可选多种页面主题。
 2. 可在本地保存自己的 `api key` 使用。
 3. 可在本地保存历史对话记录，即页面刷新不会消失，默认关闭，可在页面设置中开启。
 4. 可选择是否开启上下文连续对话，默认开启，可在页面设置中关闭。
 5. 添加删除按钮，可自己清空页面对话。
 6. 添加截图保存按钮，可点击将对话数据保存为图片。
 7. 加入语法高亮功能，同时markdown代码块实时转html标签。
 8. 代码块添加一键复制功能。
 9. 上下文对话状态下为节约 `tokens` ，当对话超过4轮后，则选取最新3轮作为上下文发送。为避免有人不点击删除按钮而导致页面积累大量对话，跟 `New Bing` 一样，当上下文对话超过20轮，则无法继续发送，会提示点击删除按钮清空页面数据！
 10. 美化页面，优化页面布局使得不同设备更好的自适应。


## 注意

1. 开发不易，拒绝白嫖，如果此小项目帮助到了您，希望能得到您的 `star` ！
2. 页面可任各位修改，希望留下项目地址，为此项目吸引更多的 `star` !
3. 项目使用开源代理：[https://github.com/geekr-dev/openai-proxy](https://github.com/geekr-dev/openai-proxy) ，点个 `star` 支持作者
4. 此项目适合小白，主打简洁，可不断完善！
5. 对于项目如有疑问，可加下面 `QQ` 群交流！
6. 体验地址：我用的是 `github pages` -> : https://aniuyyds.github.io/chat-gpt-website/
7.  部署教程：https://blog.csdn.net/qq_57421630/article/details/130040548
8.  项目后端版本：https://gitee.com/aniu-666/chat-gpt-website/tree/master/


## 学习交流 

### <font  color="#dd0000">qq 群号 ：799160455 </font>

## 项目效果

### PC端

<table>
    <tr>
        <td ><center><img src="./%E9%A1%B9%E7%9B%AE%E7%A4%BA%E4%BE%8B%E5%9B%BE/%E7%94%B5%E8%84%91%E7%AB%AF%E5%9B%BE%E7%89%87%E4%B8%80.png" width="400">图1</center></td>
        <td ><center><img src="./%E9%A1%B9%E7%9B%AE%E7%A4%BA%E4%BE%8B%E5%9B%BE/%E7%94%B5%E8%84%91%E7%AB%AF%E5%9B%BE%E7%89%87%E4%BA%8C.png" width="400">图2</center></td>
    </tr>
    <tr>
        <td ><center><img src="./%E9%A1%B9%E7%9B%AE%E7%A4%BA%E4%BE%8B%E5%9B%BE/%E7%94%B5%E8%84%91%E7%AB%AF%E5%9B%BE%E7%89%87%E4%B8%89.png" width="400">图3</center></td>
        <td ><center><img src="./%E9%A1%B9%E7%9B%AE%E7%A4%BA%E4%BE%8B%E5%9B%BE/%E7%94%B5%E8%84%91%E7%AB%AF%E5%9B%BE%E7%89%87%E5%9B%9B.png" width="400">图4</center></td>
    </tr>
</table>

### 手机端

<table>
    <tr>
        <td ><center><img src="./%E9%A1%B9%E7%9B%AE%E7%A4%BA%E4%BE%8B%E5%9B%BE/%E6%89%8B%E6%9C%BA%E7%AB%AF%E5%9B%BE%E4%B8%80.png" width="400">图1</center></td>
        <td ><center><img src="./%E9%A1%B9%E7%9B%AE%E7%A4%BA%E4%BE%8B%E5%9B%BE/%E6%89%8B%E6%9C%BA%E7%AB%AF%E5%9B%BE%E4%BA%8C.png" width="400">图2</center></td>
    </tr>
</table>