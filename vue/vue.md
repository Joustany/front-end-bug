<link href="https://cdn.bootcss.com/highlight.js/9.12.0/styles/atom-one-dark.min.css" rel="stylesheet">
<script src="https://cdn.bootcss.com/highlight.js/9.12.0/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
<style>
	.text-red {
		color: #ff2a4b;
	}
</style>
# Vue篇
1. [IOS下，touch事件无法触发](#jump1)

## 2017.06.15 <span id="jump1" class="text-red">IOS下，touch事件无法触发</span>
```html
	<div class="id" ontouchstart="iosScrollBug()" v-cloak></div>
	
	<script>
	// ios 如果父层不进行touch事件的绑定，会造成子层不触发touch事件，猜想可能是事件的传递问题
	function iosScrollBug () {
	}
	</script>
```