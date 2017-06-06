# web前端开发报告

标签（空格分隔）： 未分类

---

## 策划思路
出于对于web前端开发知识的学习，以及自身希望能够对目前HTML网页制作有一个较为直观的认识，了解自身所学，也是对于自己一个阶段性的总结。期望能够充分发挥专业知识，制作出整洁美观的网页。
本次站点内容来源于自身设计以及少量借鉴网上一些经典案例，参考了http://www.dccomics.com/，http://manhua.dmzj.com/等网站设计、


## 页面结构与说明
此次站点由4个页面构成，分别是
https://superman59.github.io/HERO/
https://superman59.github.io/HERO/%E5%85%AC%E5%8F%B8.html
https://superman59.github.io/HERO/%E5%88%97%E8%A1%A8.html
https://superman59.github.io/HERO/%E6%BC%AB%E7%94%BB.html
分别为本站点的首页、补充页、列表页与详细页。本站点的表单部分已包含于各个页面之中，不单独列出。

## 技术指标
本站点兼容IE-9以上版本，360 ，Chrome等主流浏览器.
此次站点开发使用HTML5，css3，开发工具为[Adobe Dreamweaver](http://www.adobe.com/cn/products/dreamweaver.html)，以下为浏览器兼容性，
| 浏览器        | 版本   |  兼容性  |
| --------   | -----:  | :----:  |
| IE     | IE-9 |   ✔     |
| 360        |   8.1.1.248   |   ✔   |
| Chrome Dev        |    60.0.3112.10    |  ✔  |
|火狐     | 未测试 |   ？    |

## 技术点说明
难点
一、首页css动画的效果实现，需对网页布局进行调整及实现css3的动画效果，最终通过对于z-index的改变解决了这一问题，css代码如下
```python
@keyframes hero
{
	from{opacity:1;}
	to{opacity:0;}
	0%{z-index:100;}
	99%{z-index:1;}
	100%{z-index:-110;}
}
@-webkit-keyframes hero
{
	from{opacity:1;}
	to{opacity:0;}
	0%{z-index:100;}
	99%{z-index:1;}
	100%{z-index:-110;}
}
```
二、侧边栏的实现。难点在于对于canvas的使用
解决方法如下
```python
       <canvas id="canvas" width="100%" height="100"></canvas>
        <script>
            var canvas = document.querySelector("#canvas"), image = new Image();
            var context = canvas.getContext("2d");
    
            image.onload = function() 
            {
                var pattern = context.createPattern(image, "no-repeat");
                context.arc(50, 50, 50, 0, 2 * Math.PI);
                context.fillStyle = pattern;
                context.fill();    
            };
            image.src = "pictures/super1.jpg";
        </script>
```
三、收起栏效果的实现，核心在于捕捉点击事件触发css动画，核心代码如下
```python
<input type="button" id="button1" onclick="button()" value="Click it up ▼" />
<script>
function button()
					{
						var x=document.getElementById("div1");
						x.id="div1-1";
						var y = document.getElementById("last");
						y.id="last-1";
						var z = document.getElementById("superman");
						z.id="superman-
						}
</script>
```




