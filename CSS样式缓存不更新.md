# CSS样式缓存不更新

**问题阐述：**

css样式不能及时更新

样式引用方式如下

```html
<link rel="stylesheet" id="link" href="css_js/mycss.css">
```

**解决方法：**

头部添加

```html
 <!--删除缓存-->
 <META HTTP-EQUIV="pragma"CONTENT="no-cache">
 <META HTTP-EQUIV="Cache-Control"CONTENT="no-cache,must-revalidate">
 <META HTTP-EQUIV="expires"CONTENT="0">
```

**衍生问题：**

谷歌浏览器无视标签强制缓存

**解决方法：（丐版，非完美方案）**

```html
 <link rel="stylesheet" id="link" href="css_js/mycss.css?1243">
```

在修改样式后再链接后添加“?“+任意数字

**原理：**

在问号后添加数字不影响访问位置，但会让浏览器觉得是不同的地址，于是会更新缓存

