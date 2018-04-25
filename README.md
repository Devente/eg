## 随机数
```
Math.random()*(2)+1:   1-3之间的随机数
```

## 二级联动菜单
```
<select name="city" id="c">
	<option value="">请选择</option>
</select>
<select name="content" id="c_c"></select>
<select name="content" id="c_c_1"></select>
  var c = document.getElementById('c');
	var btn = document.getElementById('bn');
	var c_content = document.getElementById('c_c');
	var c_content_1 = document.getElementById('c_c_1');
	var city = ['北京','海上','广州'];
	var content = [
		['朝阳','海淀'],
		['浦东','闵行'],
		['白云','深圳']
	];
	var xijie = [
		[
			['朝阳1','海淀1'],['朝阳2','海淀2']
		],
		[
			['浦东1','闵行1'],['浦东2','闵行2']
		],
		[
			['白云1','深圳1'],['白云2','深圳2']
		]
	];
	(function function_name(argument) {
		// body...
		btn.disabled = true;
		for (var i = 0; i < city.length; i++) {
			var option = new Option(city[i],i);
			c.appendChild(option);
		};
		c.addEventListener('change',function function_name(argument) {
			// body...
			c_content.options.length = 0;
			if (!c.value) {return}
			for (var i = 0; i < content[c.value].length; i++) {
				var c_option = new Option(content[c.value][i],i);
				c_content.appendChild(c_option)
			}
			c_content_1.options.length = 0;
			for (var j = 0; j < xijie[c.value][0].length; j++) {
				var cp_option = new Option(xijie[c.value][0][j],j);
				c_content_1.appendChild(cp_option);
			}		
		},false);
		c_content.addEventListener('change',function function_name(argument) {
			// body...
			c_content_1.options.length = 0;
			for (var i = 0; i < xijie[c.value][c_content.value].length; i++) {
				var c_option = new Option(xijie[c.value][c_content.value][i],i);
				c_content_1.appendChild(c_option);
			}
		},false)
	})()
 ```
