<link rel="stylesheet" href="http://yandex.st/highlightjs/8.0/styles/solarized_dark.min.css">
<script src="http://yandex.st/highlightjs/8.0/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
<style>
	.text-red {
		color: #ff2a4b;
	}
</style>
# CSS篇
1. [IOS，通过jquery.html()生成的元素，click事件未触发](#jump1)
2. [元素不可见，但可以点击触发事件，可能是导致了透明度为0](#jump2)
3. [Transform导致的position:fixed元素定位失效，先坍塌后复原](#jump3)

## 2016.09.29 <span id="jump1" class="text-red">ISO，通过jquery.html()生成的元素，click事件未触发</span>
```js
	/*
	解决方案
	1、在绑定click事件的元素中添加如下属性
	2、给该元素添加{ cursor: pointer; }属性
	*/
	$('.container').html('<div class="btn" onclick="javascript:;">');
```

## 2017.06.15 <span id="jump2" class="text-red">-webkit-overflow-scrolling导致的元素切换display:none; display:block;时，元素不可见，但已经出现，可以点击触发事件，可能是导致了透明度为0</span>
```html
	<style>
		.container {
			-webkit-overflow-scrolling: touch;
			/*
		    可以增加IOS下滚动的流畅度,
		    慎用,
		    可能会导致某些元素透明度为0,
		    bug级别为最高级,
		    千万不可全局设置
		  	*/
		}
	</style>
```

## 2017.06.19 <span id="jump3" class="text-red">Transform导致的position:fixed元素定位失效，先坍塌后复原</span>
```html
	<style>
		.container {
			// transition不会造成该影响
			transform: translate3d(0, 0, 0); // or transform: translate(0, 0);
		}
		
		.food-guide {
			background-color: #ffffff;
    		position: fixed;
    		z-index: 100;
    		left: 0;
    		right: 0;
    		bottom: 0;
    		width: 100%;
    		height: 90px;    		
    		display: flex;
    		box-shadow: 0 0 2px 4px rgba(221, 221, 221, 0.6);
		}
	</style>
	<div class="container">
		<div class="food-guide"></div>
	</div>
```