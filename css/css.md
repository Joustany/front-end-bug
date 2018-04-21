# CSS篇
1. [IOS，通过jquery.html()生成的元素，click事件未触发](#20160929)
2. [元素不可见，但可以点击触发事件，可能是导致了透明度为0](#20170615)
3. [Transform导致的position:fixed元素定位失效，先坍塌后复原](#20170619)
4. [微信小程序button组件自带默认样式](#20180421)

## 2016.09.29
### ISO，通过jquery.html()生成的元素，click事件未触发
```js
/*
解决方案
1、在绑定click事件的元素中添加如下属性
2、给该元素添加{ cursor: pointer; }属性
*/
$('.container').html('<div class="btn" onclick="javascript:;">');
```

## 2017.06.15
### -webkit-overflow-scrolling导致的元素切换display:none; display:block;时，元素不可见，但已经出现，可以点击触发事件，可能是导致了透明度为0
```css
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
```

## 2017.06.19
### Transform导致的position:fixed元素定位失效，先坍塌后复原
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

## 2018.04.21
### 微信小程序`<button>`组件自带默认样式
```css
button::after {
	display: none; // 隐藏默认样式
}
```