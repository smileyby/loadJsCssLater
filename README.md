#### 动态加载Javascript和Css

> 动态加载javascript方法
> 
> 方法一

```js

	function loadScript(url) {
		var script = document.createElement("script");
		script.type = "text/javascript";
		script.src = url;
		document.body.appendChild(script);
	};

	loadScript("javascript/lib/cookie.js");

```
 
> 方法二：

```js

	function loadScriptString(code){
		var script = document.createElement("script");
		script.type = "text/javascript";
		try{

			// firefox/safari/chrome/opera
			script.appendChild(document.createTextNode(code));
		}catch{
			
			// IE早起的浏览器，需要使用script的text属性来指定javascript代码
			script.text = code;
		};
		document.body.appendChild(script);
	};
	var text = "function test(){alert('test');}";
	loadScriptString(text);
	test();

```

#### 动态加载css

> 方法一

```css
	
	function loadStyles(url){
		var link = document.createElement("link");
		link.type = "text/css";
		link.rel = "stylesheet";
		link.href = url;
		document.getElementsByTagName("head")[0].appendChild(link);
	};
	loadStyles("css/secondindex.css");

```

> 方法二

```js

	function loadStyleString(cssText){
		var style = document.createElement("style");
		style.type = "text/css";
		try{
	
			// firefox/safari/chrome/opera
			style/appendChild(document.createTextNode(cssText));
		}catch{
			
			// IE早起的浏览器，需要使用style元素的stylesheet属性的cssText属性
			style.stylesheet.cssText = cssText;
		};
		document.getElementsByTagName("head")[0].appendChild(style);
	}
	var css = "body{color:blue;}";
	loadStyleString(css);

```

#### 动态加载JS和CSS的作用？（我在研究研究...(^0^)）