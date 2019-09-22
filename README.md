# pwa-genico

PWA 其中有一个能力就是把网站安装到系统桌面，以原生应用的体验来运行网站，使用户无需再找开浏览器输入网址进入网站，而是可以直接点击安装好的应用直接运行，给使网站访问缩短路径及增加网站的曝光度。

其中有一个问题就是需要生成应用的图标，通常来说需要在 `manifest.json` 的应用清单文件中配置多种尺寸的 `ico` 来适配不同分辨率的设备。而通常来说设计师只会给一个尺寸的图标。

为了解决生成不同分辨率图标的问题，这里就开发了这个应用。

## 使用
**访问地址：**

[https://lp-pwa.gitee.io/pwa-genicon/](https://lp-pwa.gitee.io/pwa-genicon/) (Gitee 托管)

[https://lecepin.github.io/pwa-genico/](https://lp-pwa.gitee.io/pwa-genicon/) (Github 托管)

**界面：**

<center><img src="https://img-blog.csdnimg.cn/20190922183840926.png" /></center>

**功能：**

- 提供 PNG 图片，勾选要生成的尺寸，可以直接进行转换生成。
- 勾选 `生成 favicon.ico` ，可用于生成浏览器支持的 `favicon.ico` 图标文件。

**示例：**

<center><img src="https://img-blog.csdnimg.cn/20190922182932589.jpg" /></center>

**配置：**

`manifest.json`，按照 icon 的尺寸和格式进行填写到 icons 属性中即可：

```json
{
  "icons": [{
    "src": "icons/256.png",
    "type": "image/png",
    "sizes": "256x256"
  }, {
    "src": "icons/192.png",
    "type": "image/png",
    "sizes": "192x192"
  }, {
    "src": "icons/144.png",
    "type": "image/png",
    "sizes": "144x144"
  }]
}
```

**注：**  `type` 必须是 `image/png`，`sizes`也必须和实际尺寸一致，且宽高是1:1。


`favicon.ico` 的话，可以直接放入站点根目录，即可生效。也可以使用如下代码：

```html
<link rel="shortcut icon" href="favicon.ico" />
```

`manifest.json` 同样也支持 `.ico` 文件，可进行多尺寸配置：

```json
{
  "icons": [{
    "src": "favicon.ico",
    "sizes": "64x64 32x32 24x24 16x16",
    "type": "image/x-icon"
  }]
}
```
