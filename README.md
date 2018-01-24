# scrollToTop
点击滚动到页面顶部

## 插件用法
```html
<script type="text/javascript" src="jquery.min.js"></script>
<script type="text/javascript" src="scrollToTop.js"></script>
<link rel="stylesheet" href="scrollToTop.css" />
```
秩序引入上面三个文件就好了。

## 插件参数配置
```javascript
$(function () {
    $(document).UItoTop({
        text: "&and;",/* 点击区域的图标或文本 */
		minScroll: 200,/* 向下滚动 minScroll 高度时出现向上图标 */
		inDelay: 600,/* 图标出现时的延时 */
		outDelay: 400,/* 图标消失时的延时 */
		containerID: "toTop",/* 向上图标的 id */
		containerIDHoverClass: "toTopHover",/*鼠标移上去时的 class*/
		scrollSpeed: 800,/* 上升时间 - 数值越大越慢*/
		easingType: "linear"/* 上升轨迹 */
    })
});
```
参数说明如上。

## 扩展
插件详情请看笔记[如何改变页面滚动到顶部的运动轨迹](http://alvinwp.com/js/431)和[animate() 方法的使用和插件 jQuery Easing 扩展](http://alvinwp.com/js/392)