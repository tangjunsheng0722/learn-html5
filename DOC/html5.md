# HTML5
> 为 HTML5 建立的一些规则：
```
新特性应该基于 HTML、CSS、DOM 以及 JavaScript。
减少对外部插件的需求（比如 Flash）
更优秀的错误处理
更多取代脚本的标记
HTML5 应该独立于设备
开发进程应对公众透明
```
> HTML5 中的一些有趣的新特性
```
用于绘画的 canvas 元素
用于媒介回放的 video 和 audio 元素
对本地离线存储的更好的支持
新的特殊内容元素，比如 article、footer、header、nav、section
新的表单控件，比如 calendar、date、time、email、url、search
```
## 视频 video
> controls 属性供添加播放、暂停和音量控件
```
<video src="movie.ogg" controls="controls">
</video>
```
> video 元素允许多个 source 元素。source 元素可以链接不同的视频文件。浏览器将使用第一个可识别的格式
```
<video width="320" height="240" controls="controls">
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
```
> autoplay 自动播放 control 控件 height/width 视频宽高 loop循环播放 preload 预播放 src 视频url
## 视频 DOM
```
function playPause()
{
if (myVideo.paused)
  myVideo.play();
else
  myVideo.pause();
}

function makeBig()
{
myVideo.width=560;
}

function makeSmall()
{
myVideo.width=320;
}

function makeNormal()
{
myVideo.width=420;
}
```
## 音频 audio
```
<audio controls="controls">
  <source src="song.ogg" type="audio/ogg">
  <source src="song.mp3" type="audio/mpeg">
Your browser does not support the audio tag.
</audio>
```
> 与视频一样的控件属性
## 拖放
## 画布 canvas
```
<canvas id="myCanvas" width="200" height="100"></canvas>
<script type="text/javascript">
var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d");
cxt.fillStyle="#FF0000";
cxt.fillRect(0,0,150,75);
</script>
```
## SVG
> SVG 指可伸缩矢量图形 (Scalable Vector Graphics);   SVG 用于定义用于网络的基于矢量的图形; SVG 使用 XML 格式定义图形; SVG 图像在放大或改变尺寸的情况下其图形质量不会有损; SVG 是万维网联盟的标准
```
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" height="190">
  <polygon points="100,10 40,180 190,60 10,60 160,180"
  style="fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;" />
</svg>
```
## 地理位置
> 请使用 getCurrentPosition() 方法来获得用户的位置
```
<script>
var x=document.getElementById("demo");
function getLocation()
  {
  if (navigator.geolocation)
    {
    navigator.geolocation.getCurrentPosition(showPosition);
    }
  else{x.innerHTML="Geolocation is not supported by this browser.";}
  }
function showPosition(position)
  {
  x.innerHTML="Latitude: " + position.coords.latitude +
  "<br />Longitude: " + position.coords.longitude;
  }
</script>
```
## web 存储
> 在session中详细介绍
## html5 表单
> 类型
```
E-mail: <input type="email" name="user_email" />
Homepage: <input type="url" name="user_url" />
Points: <input type="number" name="points" min="1" max="10" />
<input type="range" name="points" min="1" max="10" />
Date: <input type="date" name="user_date" />
<input type="search" name="user_date" />
```
> 表单元素 datalist keygen output
```
Webpage: <input type="url" list="url_list" name="link" />
<datalist id="url_list">
<option label="W3School" value="http://www.W3School.com.cn" />
<option label="Google" value="http://www.google.com" />
<option label="Microsoft" value="http://www.microsoft.com" />
</datalist>

<form action="demo_form.asp" method="get">
Username: <input type="text" name="usr_name" />
Encryption: <keygen name="security" />
<input type="submit" />
</form>

<output id="result" onforminput="resCalc()"></output>
```
> 表单属性
```
// form 属性
autocomplete
novalidate
// input属性
autocomplete
autofocus
form
form overrides (formaction, formenctype, formmethod, formnovalidate, formtarget)
height 和 width
list
min, max 和 step
multiple
pattern (regexp)
placeholder
required
```