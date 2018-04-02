# scrollToTop：点击滚动到页面顶部

## 插件用法
```html
<script type="text/javascript" src="jquery.min.js"></script>
<script type="text/javascript" src="scrollToTop.min.js"></script>
```
引入上面两个文件之后，即可调用该插件了：
```javascript
$(function () {
    $(document).scrollToTop(); //不改变默认参数的用法
});
```

## 插件参数配置
```javascript
$(function () {
	$(document).scrollToTop({
		/********** 标签属性设置 **********/
		targetNodeID: "scrollToTop",/* 绑定 scrollTop 事件的元素（targetNode） id */
		targetNodeClass: "scrollToTop",/* 绑定 scrollTop 事件的元素（targetNode） class */
		targetNodeHoverClass: "on",/* 鼠标 hover 时 targetNode 新增的 class */
		targetNodeText: "",/* targetNode 的文本，可以填入 html 字段 */
		targetNodeTitle: "Back to Top",/* targetNode 的文本 */
		minScrollTop: 200,/* 向下滚动 minScrollTop 高度时出现图标 */
		inDelay: 600,/* 图标出现时的延时 */
		outDelay: 400,/* 图标消失时的延时 */
		scrollSpeed: 1200,/* 上升时间 - 数值越大越慢 */
		scrollToWhere: 0,/* 滚动到距离页面顶端 scrollToWhere 的地方 */
		easingType: "easeOutQuart",/* scroll 的轨迹（easeInQuart/easeOutQuart/easeInOutQuart）*/
		/********** 样式属性设置 **********/
		targetNodeWidth: "50", /* targetNode 默认宽度 */
		targetNodeHeight: "50", /* targetNode 默认高度 */
		targetNodePsBottom: "5%", /* targetNode 默认里底部的位置 */
		targetNodePsRight: "2%", /* targetNode 默认里顶部的位置 */
		targetNodeMgTop: "", /* targetNode 默认的 margin-top */
		targetNodeMgRight: "", /* targetNode 默认的 margin-right */
		targetNodeBgColor: "#ddd", /* targetNode 默认的背景色 */
		targetNodeFtColor: "#666", /* targetNode 默认的字体颜色 */
		targetNodeHoverBgColor: "#ccc", /* targetNode 默认 hover 状态的背景色 */
		targetNodeHoverFtColor: "#444", /* targetNode 默认 hover 状态的字体颜色 */
		targetNodeBrRadius: "50%", /* targetNode 默认的倒角 */
		targetNodeOpacity: 1, /* targetNode 默认的透明度 */
		targetNodeHoverOpacity: 1, /* targetNode 默认的 hover 状态的透明度 */
		/********** targetNode 里 icon（利用 border 画出的小三角）样式 **********/
		targetIconBrWidth: 8, /* targetNode 里 icon 的边框粗细 */
		targetIconBrColor: "#aaa" /* targetNode 里 icon 的边框颜色 */
	})
});
```
- **scrollToWhere**: 滚动到距离页面顶部 scrollToWhere 处停下；默认值是 0，即默认滚动到页面顶部；
- **targetNodeText**：绑定了滚动事件的元素的 html() 内容；若为空，即默认出现向上箭头；
- **easingType**：滚动的轨迹，默认值是 easeOutQuart；本插件调用 jQuery.easing 的方法提供了 easeInQuart/easeOutQuart/easeInOutQuart 三种轨迹；可通过下面的代码继续扩展滚动轨迹：
  ```javascript
  jQuery.extend(jQuery.easing, {
		easeInQuart: function (x, t, b, c, d) {
			return c * (t /= d) * t * t * t + b
		},
		easeOutQuart: function (x, t, b, c, d) {
			return -c * ((t = t / d - 1) * t * t * t - 1) + b
		},
		easeInOutQuart: function (x, t, b, c, d) {
			if ((t /= d / 2) < 1) {
				return c / 2 * t * t * t * t + b
			}
			return -c / 2 * ((t -= 2) * t * t * t - 2) + b
		}
   });
  ```
- 其余参数比较简单，可看后面的相关注释

## 插件示例
[Demo](https://alvinyw.github.io/Blog/DsScrollToTop/scrollToTop.html)

## 插件扩展
插件详情请看笔记 [如何改变页面滚动到顶部的运动轨迹](http://alvinwp.com/js/431) 和 [animate() 方法的使用和插件 jQuery Easing 扩展](http://alvinwp.com/js/392)