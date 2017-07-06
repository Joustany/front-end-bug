# Vue篇
1. [IOS下，touch事件无法触发](#2017.06.15)

## 2017.06.15 
### IOS下，touch事件无法触发
```html
<div class="id" ontouchstart="iosScrollBug()" v-cloak></div>
	
<script>
// ios 如果父层不进行touch事件的绑定，会造成子层不触发touch事件，猜想可能是事件的传递问题
function iosScrollBug () {
}
</script>
```