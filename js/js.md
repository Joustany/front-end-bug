# JS篇
1. [JS一键复制 sfarai HACK](#20180313)

## 2018.03.13
### JS一键复制 sfarai HACK
```js
// 思路：要想复制到剪贴板，必须先选中这段文字。
function copyNum() {
	var NumClip=document.getElementById("clip_num");
	var NValue=NumClip.value;
	var valueLength = NValue.length;
	selectText(NumClip, 0, valueLength);
	document.execCommand("Copy","false",null); // 执行浏览器复制命令
	alert("已复制,可分享给朋友啦，试试看。");
}
// input自带的select()方法在苹果端无法进行选择，所以需要自己去写一个类似的方法
function selectText(obj, startIndex, stopIndex) {
    if (obj.setSelectionRange) {
        obj.setSelectionRange(startIndex, stopIndex);
    } else if (obj.createTextRange) {
        var range = obj.createTextRange();
        range.collapse(true);
        range.moveStart('character', startIndex);
        range.moveEnd('character', stopIndex - startIndex);
        range.select();
    }
    obj.focus();
}
```