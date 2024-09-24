# Day 1

## html

1.  VS code 模板快捷键： ！

	格式化 ctrl+alt+l

2.  `./`  `../`

	正斜杠 & 反斜杠（win路径）

	<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240525210346215.png" alt="image-20240525210346215" style="zoom:50%;" />

3.  width height % 相对于父元素的百分比

4.  \<hr>
	水平分割线

5. CSS**三种**引入方式

![image-20240525211731436](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240525211731436.png)

6. 在十六进制系统中，`cc` 表示的值是十进制的 204。

7. CSS三种选择器：优先级id> 类> 元素

8. ` &nbsp` 是一个 HTML 实体，它的全称是 "non-breaking space"。

9. 页面布局标签

- \<span>\</span>
	-  一行当中可以有多个span标签
	-  宽高默认由内容撑开
	-  不可以设置宽高
- \<div>\</div>
	- 独占一行
	- 宽度默认父元素宽，高度默认内容撑开
	- 可以设置宽高

10. 盒子模型

	红框为实际的盒子

	<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240525225445112.png" alt="image-20240525225445112" style="zoom: 33%;" />

```css
<style>
	div {
		width: 200px; /* 宽度 */
		height: 200px; /* 高度 */
		box-sizing: border-box; /* 指定width height为盒子的高宽,默认为content的高宽 */
		background-color: aquamarine; /* 背景色 */
		padding: 20px 20px 20px 20px; /* 内边距, 顺时针 上 右 下 左 , 边距都一行, 可以简写											  padding: 20px;*/
		border: 10px solid red; /* 边框, 宽度 线条类型 颜色 */
		margin: 30px 30px 30px 30px; /* 外边距, 上 右 下 左 , 边距都一行, 可以简写: margin: 										30px; */
		}
</style>
```

盒子的居中可以通过设置margin的左右的值来实现  margin: 0  auto;



11. **表单标签:  <form>**

- 表单属性:

	- action: 规定表单提交时，向何处发送表单数据，表单提交的URL，如果不指定，默认提交到当前页面
	- method: 规定用于发送表单数据的方式，常见两种请求方式为： GET、POST
		- GET（default）：表单数据是拼接在url后面的， 如： xxxxxxxxxxx?username=Tom&age=12，url中能携带的表单数据大小是有限制的。
		- POST： 表单数据是在请求体（消息体）中携带的，大小没有限制。

- 表单项标签: 不同类型的input元素、下拉列表、文本域等。

	- input: 定义表单项，通过==type属性控制输入形式==,  必须有name属性才能进行提交，

		​		   属性value定义提交的值

		![image-20240526003826260](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526003826260.png)

		-  用户名: <input type="text" name="username">

		- <input type="submit" value="提交">

			type定义提交按钮，value定义按钮上显示的文字

		- <label><input type='radio' name='gender' value='1'>女</label>

			使用label的意义是当鼠标点击文字时，radio按钮也会被选中

	- select: 定义下拉列表

	- textarea: 定义文本域

- payload

	**HTTP 请求中的 `payload`**

	在HTTP请求中，`payload` 通常是指请求主体（request body），包含客户端发送到服务器的实际数据。这在POST、PUT、PATCH等方法中尤为常见，例如：

	- **表单数据**：当用户在网页上填写表单并提交时，表单数据会作为 `payload` 发送到服务器。
	- **JSON 数据**：在许多Web应用程序中，客户端会通过AJAX请求发送JSON格式的数据到服务器。

​	  **HTTP 响应中的 `payload`**

​		在HTTP响应中，`payload` 是指响应主体（response body），包含服务器返回给客户端的实际数据。这可以		是HTML内容、JSON数据、图像、文件等。





# Day 2

1. JS 的特点

- 跨平台：在不同的操作系统上运行
- 面向对象
	- **封装**（Encapsulation）：将数据和操作数据的方法封装在对象中，对象的内部状态只能通过公开的方法进行访问和修改，隐藏了内部实现细节。
	- **继承**（Inheritance）：通过继承机制，新的类可以继承现有类的属性和方法，促进代码重用和扩
	- **多态**（Polymorphism）：允许不同类型的对象以相同的接口进行操作，提高代码的灵活性和可扩展性。
	- **类和对象**：类是对象的蓝图，定义了对象的属性和行为；对象是类的实例，包含实际的数据和方法实现。
- 脚本语言：大多数脚本语言是解释型的，代码在运行时由解释器逐行执行，而不是事先编译为二进制代码。

2. 两种引入方式：内部 & 外部

3. 三种输出方式

![image-20240526013034708](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526013034708.png)

4. 三个变量关键字

<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526013243721.png" alt="image-20240526013243721" style="zoom:50%;" />

- var 全局，可重复定义

	```javascript
	var x=1;
	var x='A';
	```

- let 局部变量，不能重复定义

5. 数据类型

<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526013803724.png" alt="image-20240526013803724" style="zoom:50%;" />


​	

6. 运算符

​	==：只比较值是否相等，不区分数据类型，哪怕类型不一致，也会自动转换类型进行值的比较

​	===：不光比较值，还要比较类型，如果类型不一致，直接返回false

7. 类型转换

```javascript
- 字符串转换成数字: parseInt
```

- 其他类型转为boolean：0,NaN,"",null,undefined(未定义变量) 理解成false,反之理解成true



8. 函数

```javascript
//第一种定义
function 函数名(参数1,参数2..){
	//要执行的代码
}

//第二种定义
var functionName = function (参数1,参数2..){ 
 	//要执行的代码
}
```

- 形式参数不需要声明类型，并且JavaScript中不管什么类型都是let或者var去声明，加上也没有意义。

- 返回值也不需要声明类型，直接return即可

- 在调用函数时可以传递任意个数的参数


​		

 9.  对象：基本对象、BOM对象、DOM对象

	<figure class="third">
	 <div class="image-container" style="display: inline-block; width: 32%;  box-sizing: border-box;">
			<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526064113559.png" alt="***"  />
	     <figcaption style="text-align: center; font-weight: bold;margin-top:10px;">基本对象</figcaption>
	  </div>
	 <div class="image-container" style="display: inline-block; width: 32%; box-sizing: border-box;">
			<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526064317868.png" alt="***"  />
	     <figcaption style="text-align: center;font-weight: bold;margin-top:10px;">BOM</figcaption>
	  </div>
	 <div class="image-container" style="display: inline-block; width: 32%; box-sizing: border-box;">
			<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526064430402.png" alt="***"  />
	     <figcaption style="text-align: center;font-weight: bold;margin-top:10px;">DOM</figcaption>
	  </div>
	</figure>



10. 数组

	- JS数组类似 Java 集合 ：长度可变、类型可变

	- ```javascript
		//forEach: 遍历数组中有值的元素
		arr.forEach(function(e){
		    console.log(e);
		})
		/*数组遍历：forEach方法遍历数组arr中的每个元素e。
		回调执行：对于数组中的每个元素e，forEach方法都会调用传入的回调函数，并将当前元素作为参数传递给匿名回调函数。
		控制台输出：在回调函数中，console.log(e)被执行，输出当前元素的值到控制台*/
		
		
		//箭头函数：省略关键字function，引入箭头，简化函数定义语法
		arr.forEach((e) => {
			console.log(e);
		})
		
		```

11. 字符串

	- substring(start, end)   左闭右开

12. JS 对象  

	```javascript
	var 对象名 = {
		属性名1: 属性值1,
		属性名2: 属性值2,
		属性名3: 属性值3,
		函数名称: function(形参列表){}
	};
	```

	

	JSON对象 (JavaScript Object Notation）：通过JS对象标记法书写的==文本==,本质上是==字符串==！！！

	```json
	//JSON定义用单引号包起来
	var 变量名= '{
		"key":value,
		"key":value,
		"arr":[value,...]
	}'
	
	```

	- **key 必须使用引号并且是双引号标记**

	- usage

		- 数据交换: 通常用于在客户端和服务器之间传递数据

		- 配置文件

		- 数据储存

	- JSON字符串与JS对象的转换

		- var jsObj = JSON.parse(jsonstr);

			先parse成object再进行对象属性的获取

		- var jsonStr = JSON.stringfy(jsObject);

			

13. BOM（Browser Object Model） JavaScript 将浏览器的各个组成部分封装成了对象

	![image-20240526095144242](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526095144242.png)

	<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526101407670.png" alt="image-20240526101407670" style="zoom: 50%;" />

	

	- ```javascript
		//confirm - 对话框 -- 确认: true , 取消: false
		var flag = confirm("您确认删除该记录吗?");
		alert(flag);
		```

	- location

		- **location.href**   设置or返回地址 



14. DOM对象：Document Object Model 文档对象模型。也就是 JavaScript 将 HTML 文档的各个组成

	部分封装为对象。

![image-20240526100615749](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526100615749.png)

- 先获取对象
- 再查看参考手册对对象进行操作



15. 事件

	- 两种事件绑定方式

		<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526113245812.png" alt="image-20240526113245812" style="zoom:50%;" />

		- `onclick`是一个==HTML DOM事件==，它属于所有支持点击事件的HTML元素的属性，而不是某个特定对象（如button或mouse）的独有属性。在HTML DOM中，许多元素都可以有点击事件，这包括但不限于`<button>`、`<a>`、`<div>`等元素。因此，`onclick`属性可以应用于这些支持点击事件的元素。

			具体来说：

			**`onclick` 属性** 

			`onclick`属性可以应用于许多不同的HTML元素，而不仅仅是按钮或鼠标。例如：

			- **按钮** (`<button>`)：用户点击按钮时触发`onclick`事件。
			- **链接** (`<a>`)：用户点击超链接时触发`onclick`事件。
			- **图片** (`<img>`)：用户点击图片时触发`onclick`事件。
			- **任何其他可点击元素**：如`<div>`、`<span>`等

	16. Vue

	- Vue.js 是一套构建用户界面的 **渐进式框架**。Vue 的核心库只关注视图层，并且非常容易学习，非

		常容易与其它库或已有项目整合。Vue.js 的目标是通过尽可能简单的 API 实现**响应的数据绑定**和**组**

		**合的视图组件**。

		==框架即是一个半成品软件==，是一套可重用的、通用的、软件基础代码模型。基于框架进行开发，更加快捷、更加高效。

		

	- **MVVM**: Model-View-ViewModel

		- Model: 数据模型，特指前端中通过请求从后台获取的数据

		- View: 视图，用于展示数据的页面，可以理解成我们的html+css搭建的页面，但是没有数据

		- ViewModel: 数据绑定到视图，负责将数据（Model）通过JavaScript的DOM技术，将数据展

		示到视图（View）上

		<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526153435559.png" alt="image-20240526153435559" style="zoom:33%;" />

	- Vue2 使用步骤

		- 将vue.js拷贝到js目录

		- 然后编写<script>标签来引入vue.js文件

			```javascript
			<script src="js/vue.js"> </script>
			```

		- 在js代码区域定义vue对象

			```javascript
			<script>
			//定义Vue对象
				new Vue({
				el: "#app", //vue接管区域
				data:{
					message: "Hello Vue"
					 }
				})
			</script>
			
			/*属性：
			el:element 用来指定哪儿些标签受 Vue 管理。
				这个属性用于指定Vue实例的挂载点，它可以是一个CSS选择器字符串，也可以是一个直接的DOM元素。通过el属性，Vue实例将控制指定的DOM元素及其子元素。
				该属性取值 #app 中的 app 需要是受管理的标签的id属性值
			
			data: 用来定义数据模型
			methods: 用来定义函数。这个我们在后面就会用到*/
			```

		- 在html区域编写视图，其中`{{ }}`是==插值表达式==，用来将vue对象中定义的model展示到页面上的

	- Vue 指令

	  <img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526160455947.png" alt="image-20240526160455947" style="zoom:50%;" />

	  - v-if : 按条件渲染

	  - v-show: 按条件展示   不展示的标签：<span style="display:none;"></span>

	  - v-bind 可以用 ` :` 省略代替

	    - 可用于设置标签（展示）的data属性

	    	<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240530150845700.png" alt="image-20240530150845700" style="zoom:50%;" />

	  - v-on 可以用 ` @` 省略代替

	  	

	- Vue生命周期
	
		- 在Vue.js中,==挂载（mounting）==是指==将Vue实例与DOM元素关联==起来，并让Vue实例控制该元素及其子元素的过程。挂载后，Vue实例可以管理和更新DOM中的内容，从而实现数据的响应式更新和界面的动态渲染。
		- 应用：页面的数据应该是==页面加载完成，自动发送请求，展示数据，==所以我们需要借助vue的mounted钩子函数。
		- 在编程中，==钩子方法（Hook Method）==是指可以在特定时刻或事件发生时自动调用的方法。它允许开发者在这些特定的时刻插入自己的代码，以实现特定的功能或行为。

![image-20240526213105519](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240526213105519.png)



# Day 3

1. **Ajax**: Asynchronous JavaScript And XML，异步的JavaScript和XML

- 与服务器进行数据交换：通过Ajax可以==给服务器发送请求==，并获取服务器响应的数据。

- 异步交互：可以在**不重新加载整个页面**的情况下，与服务器交换数据并**更新部分网页**的技术，如：

搜索联想、用户名是否可用的校验等等。

2. 同步异步请求

- 同步：浏览器页面在发送请求给服务器，在服务器处理请求的过程中，浏览器页面==不能做其他的操作==。只

	能等到服务器响应结束后才能，浏览器页面才能继续做其他的操作。

- 异步：浏览器页面发送请求给服务器，在服务器处理请求的过程中，浏览器页面还可以做其他的操作。

3. 客户端的Ajax请求

- 创建XMLHttpRequest对象，用于和服务器交换数据，也是原生Ajax请求的核心对象，提供了各种方法。

	```javascript
	var xmlHttpRequest = new XMLHttpRequest();
	```

- 调用对象的==open()==方法==设置请求的参数==信息，例如请求地址，请求方式。然后调用send()方法向服务器发送请求

	```javascript
	//2. 设置请求参数+发送异步请求
	xmlHttpRequest.open('GET','http://yapi.smartxwork.cn/mock/169327/emp/list');
	xmlHttpRequest.send();
	```

- 通过绑定事件的方式，获取服务器响应的数据

	```javascript
	//3. 获取服务响应数据
	xmlHttpRequest.onreadystatechange = function(){
		if(xmlHttpRequest.readyState == 4 && xmlHttpRequest.status ==200){
			document.getElementById('div1').innerHTML =	xmlHttpRequest.responseText;
		 }
	}
	```

- 每次 readyState 改变时都会调用 onreadystatechange 函数。

- onreadystatechange 事件被触发了四次（1-4），每次 readyState 变化一次。

- 当 readyState 为 `4` 且 status 为 `200` 时，响应就绪：

![image-20240527105128341](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240527105128341.png)

4. 原生的Ajax请求的代码编写起来还是比较繁琐的，==Axios==是对原生的AJAX进行封装，简化书写。

- 引入Axios文件

	```javascript
	<script src="js/axios-0.18.0.js"></script> 
	```

- 使用Axios发送请求，并获取响应结果

	- 发送 get 请求

		```javascript
		axios({
			method:"get",
			url:"http://localhost:8080/ajax-demo1/aJAXDemo1?username=zhangsan"
		}).then(function (resp){
			alert(resp.data);
		})
		
		//请求方式别名
		axios.get("http://yapi.smart-xwork.cn/mock/169327/emp/list").then(result => {console.log(result.data);})
		```

		- 浏览器访问地址通常是通过 HTTP 的==GET==方法进行访问

	- 发送 post 请求

		```javascript
		axios({
			method:"post",
			url:"http://localhost:8080/ajax-demo1/aJAXDemo1",
			data:"username=zhangsan"
		}).then(function (resp){
			alert(resp.data);
		});
		
		//请求方式别名
		axios.post("http://yapi.smartxwork.cn/mock/169327/emp/deleteById","id=1").then(result => {console.log(result.data);})
		```

		- url属性：用来书写请求的资源路径。如果是 get 请求，需要将请求参数拼接到路径的后面，格式为： url?参数名=参数值&参数名2=参数值2。
		
		- data属性：作为请求体被发送的数据。也就是说如果是 post 请求的话，数据需要作为data 属性的值。
		
			`res` 是 Axios 的响应对象。
		
			`res.data` 是从服务器返回的响应体。
		
			`res.data.data` 是服务器响应体中的 `data` 属性，通常包含需要使用的具体数据。
		
		- then() 需要传递一个匿名函数。我们将 then()中传递的匿名函数称为 **回调函数**，意思是该匿名函数在发送请求时不会被调用，而是在==成功响应后调用的函数==。而该回调函数中的 ==resp 参数是对响应的数据进行封装的对象==，通过 resp.data 可以获取到响应的数据。



5.  **接口文档**：前后台开发人员都 需要遵循这套规范开发。接口文档的内容由后台开发者根据产品经理提供的产品原型和需求文档所撰写出来。

	![image-20240527171844950](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240527171844950.png)

	- 在线文档平台：YAPI
		- API接口管理：根据需求撰写接口，包括接口的地址，参数，响应等等信息。
		- Mock服务：模拟真实接口，生成接口的模拟测试数据，用于前端的测试。

6. **前端工程化**

<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240527190616939.png" alt="image-20240527190616939" style="zoom: 50%;" />

- 通过vue官方提供的脚手架Vue-cli来完成

	- 统一的目录结构

	- 本地调试
	- 热部署 : 
		- Web开发中，开发人员可以在修改代码后立即看到变化,无需重新运行程序，常用于前端框架（如React、Angular）和后端服务器（如Spring Boot、Node.js）
	- 单元测试
	- 集成打包上线

7. 脚手架

>- 脚手架是一种用在建筑领域的辅助工具，或者说是为了保证各施工过程顺利进行而搭设的工作平台
>
>	对应到软件工程领域，脚手架可以解释为帮助开发人员在开发过程中使用的==开发工具、开发框架==，使用脚手架你无须从头开始搭建或者编写底层软件。
>
>- Principles
>
>	>-  DRY原则（Don't Repeat Yourself）：DRY原则直译过来就是“不要重复你自己”。这一原则和复用原则类似，强调尽量在项目中减少重复的代码行、重复的方法、重复的模块。
>	>
>	>-  开闭原则（Open Close Principle）：开闭原则中的“开”就是指对功能的扩展是开放的，“闭”是指对于原有代码的修改是封闭的。通俗一点讲，软件系统通常是由各种模块组成的，软件系统在增加一项新的功能时，应该在不修改现有代码的基础上操作。
>
>- 常用脚手架
>
>	>- **Vue框架**
>	>- **Maven**: 是一个==跨平台的项目管理工具==，是服务于Java平台的项目构建、依赖管理、项目信息管理工具。同时使用Maven可以规范项目骨架及包层次结构、命名配置文件、生成代码原型等。
>	>- **Netty**
>	>- **Java EE**



8. Node.js

- **Node.js** 是一个基于 Chrome V8 引擎的 JavaScript 运行时环境，它允许开发者==使用 JavaScript==编写服务器端应用程序

- **npm**（Node Package Manager）是 ==Node.js 的包管理工具和软件库==。它是随 Node.js 一起安装的，并且是 JavaScript 生态系统中最大的包管理器。

	- **TIPS**  VsCode侧栏打开npm需要先点一下项目中的`package.json`文件

		```javascript
		"scripts": {
		    "serve": "vue-cli-service serve",
		    "build": "vue-cli-service build",
		    "lint": "vue-cli-service lint"
		  }
		```

- ==npm 的淘宝镜像==是由淘宝团队（阿里巴巴）提供的一个 npm registry 镜像，目的是提高 npm 包管理工具在国内的下载速度和稳定性。由于官方 npm registry 服务器在国外，国内用户在使用 npm 安装包时可能会遇到速度慢、连接不稳定等问题。淘宝镜像通过将 npm registry 的内容同步到国内服务器，显著提升了国内用户的体验。

- 命令 `npm install -g @vue/cli` 用于全局安装 Vue.js CLI 工具

	**g- global全局安装**的包可以在命令行中直接使用，而不需要在每个项目中单独安装

- 目录结构

	<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240527210120010.png" alt="image-20240527210120010" style="zoom:50%;" />

	

- npm run serve 

	> - #### Local: http://localhost:8080/
	>
	> 指向==本地计算机上运行的一个 Web 服务器==的地址。
	>
	> 在本地计算机上运行的一个 Web 服务器意味着你的==计算机本身作为服务器运行，提供 Web 服务==。它可以处理和响应 HTTP 请求，就像一个在线的 Web 服务器一样。常见的 Web 服务器软件有 Apache、Nginx 和轻量级的开发服务器如 Node.js、Python 的 Flask/Django 等。
	>
	>  **Web 服务器的基本概念**
	>
	> > - **Web 服务器**：一种软件或硬件，负责接收客户端（如浏览器）发送的 HTTP 请求，并返回相应的 HTTP 响应（通常是网页内容）
	>
	> **在本地计算机上运行 Web 服务器的用途**
	>
	> > - **开发和测试:** 开发人员可以在本地运行 Web 服务器进行应用程序的开发和测试，而不必将应用程序部署到远程服务器上。
	>
	> 
	>
	> 1. **http**
	>
	> - 这是 URL 的协议部分，表示使用 HTTP（超文本传输协议）进行通信。HTTP 是用于 Web 浏览器和服务器之间通信的标准协议。
	>
	> 2. **localhost**：
	>
	> - `localhost` 是一个特殊的域名，指向本地计算机的回环地址（通常是 127.0.0.1）。当你访问 `localhost` 时，实际上是在访问==自己计算机上的网络服务==。
	>
	> 3. **8080**：
	>
	> - 这是端口号，指定要连接到的网络端口。默认情况下，HTTP 服务器使用端口 80，但为了避免冲突或出于其他目的，服务器可以配置为使用不同的端口，比如 8080
	>
	> - 修改端口号(vue.config.js)：
	>
	> 	```javascript
	> 	devServer:{
	> 	  port:7000
	> 	 }
	> 	```
	>
	> 
	>
	> 4. **/**：
	>
	> - 斜杠 `/` 表示请求根路径，即服务器上的默认资源或主页
	>
	> 
	>
	>  **典型使用场景**
	>
	> 1. **本地开发**：
	>
	> 	- 在 Web 开发中，开发者通常在本地计算机上运行一个 Web 服务器，用于测试和调试。服务器可能使用像 Node.js、Python Flask、Django、Apache 或 Nginx 等技术。
	> 	- 例如，如果你使用 Node.js 和 Express.js 创建了一个 Web 服务器，并在端口 8080 上运行，你可以在浏览器中访问 `http://localhost:8080/` 来查看你的应用。
	>
	> 
	>
	> - ####  Network: http://192.168.1.50:8080/
	>
	> 	**192.168.1.50**：
	>
	> 	- 这是 IP 地址，表示网络中的某个特定设备。`192.168.1.50` 是一个典型的私有 IP 地址，通常用于局域网（LAN）中的设备。
	> 	- `192.168.x.x` 是一个常见的私有 IP 地址范围，常用于家庭和办公室网络。
	>
	> 	**应用场景**
	>
	> 	- 假设你在家或办公室内，有一个运行在 IP 地址为 `192.168.1.50` 上的设备（如计算机、服务器、路由器或物联网设备）。该设备上运行了一个 Web 服务，并监听 8080 端口。通过在浏览器中访问 `http://192.168.1.50:8080/`，你可以与该服务进行交互。



9. Vue 开发流程：

- index.html文件默认引入了入口函数main.js文件

- 默认展示根组件APP.vue

	如想使用其他组件需要在APP.vue中引入该组件

- ```javascript
	import Vue from 'vue'
	import App from './App.vue'
	import router from './router'
	
	Vue.config.productionTip = false
	
	//1.$mount('#app')将vue对象创建的dom对象挂在到id=app的这个标签区域中，作用和之前学习的vue对象的le属性一致。
	new Vue({
		router,
		render: h => h(App)
	}).$mount('#app')
	
	//另一种写法
	new Vue({
	    el:"#app",
		router:router,
		render: h => h(App)
	})
	```

- .vue结尾的是vue组件文件

	- template: ==模板部分==，主要是HTML代码，用来展示页面主体结构的

	- script: js代码区域，主要是通过js代码来控制模板的==数据来源和行为==的

		```javascript
		<script>
		//在这里export，其他文件才能import
		//之前直接定义data对象，但这里定义的是data函数，并且要返回函数里的对象message，这样做主要是为了确保每个组件实例都有独立的状态（数据），旨在避免在组件复用时产生数据共享问题。
		
		export default {
			data(){
				return {
					"message":"hello world"
				 }
			 }
		}
		
		//previous version
		new Vue({
		    el:"#app",
		    data:{
		        message:"Hello Vue"
		    }
		})
		```

	- style: css样式部分，主要通过css样式控制模板的页面效果得

- Vue组件库 Element

  - 在项目路径下安装组件库npm install element-ui@2.15.3 

  - 在views文件夹下创建ElementView.vue 必须采用驼峰命名法，否则会报错

  - 将组件代码复制在<template></template>中

  - 在根组件文件App.vue的template中的div block引入<element-view></element-view>

  	**TIPS：**要打出 `<` 才能实现在<scipt></script>自动联想导入（控制template的数据来源）

  	还有一个坑是：必须要在联想导入前将<scipt></script>设置成这个格式，少了`export default {} `也无法正确导入的

  	```javascript
  	<script>
  	export default {
  	}   
  	</script>
  	```

  	导入后：

  	```javascript
  	<script>
  	import ElementView from './views/ElementView.vue'
  	export default {
  	  components: { ElementView },
  	  data() {
  	    return {
  	      
  	    }
  	  },
  	}   
  	</script>
  	```

  

- Element分类

	- 引入多个element组件应该把他们包在同一个div block下，否则会报错

	- ```javascript
		//定义事件时，省略括号避免在methods定义方法接收变量时报错
		@size-change="handleSizeChange"
		@size-change="handleSizeChange()"
		
		//两种写法
		methods:{
		        handleSizeChange(val){
		            alert("每页记录数变化" + val)
		        },
		        handleCurrentChange:function(val){
		            alert("页码发生变化" + val)
		        }
		    }
		```

	- 点击按钮呈现对话框用到dialog组件

	- 表单form 数据模型定义，形式为一个对象

		在onSubmit函数中要将该vue实例的form中内容显示出来，需要将对象stringfy

		<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240528221948990.png" alt="image-20240528221948990" style="zoom:50%;" />

	- 异步加载数据，需要使用axios发送ajax请求

		在vue项目中，对于axios的使用，分为如下2步：

		- 在项目路径下安装axios:`npm install axios` 

		- 需要使用axios时，导入axios: `import axios 'axios'`

		- 在加载页面时显示数据，需要用到钩子方法mounted()

			TIPS: mountd()应该是和methods()平级的！！别写在methods()里面！！

			<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240529104131725.png" alt="image-20240529104131725" style="zoom:50%;" />

	- > label	页面上显示的标签名
		>
		> prop	对应列内容的字段名

	10. **案例**：根据页面原型完成员工管理页面开发，并通过Axios完成数据异步加载

	- 创建页面，完成页面的整体布局规划

	- 布局中各个部分的组件实现

	- 列表数据的异步加载，并渲染展示

		

	11. **Vue 路由**

	前端路由：**URL中的hash(#号之后的内容）与组件之间的对应关系**

	![image-20240530153041662](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240530153041662.png)

​		 **路由插件Vue Router**

> VueRouter：路由器类，根据路由请求在路由视图中动态渲染选中的组件
>
> <router-link>：请求链接组件，浏览器会解析成<a>
>
> <router-view>：动态视图组件，用来渲染展示与路由路径对应的组件

![image-20240530153757741](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240530153757741.png)

TIPS:

1. 在router路径下 index.js

	```javascript
	const routes = [
	  {
	    path: '/dept',
	    name: 'dept',
	    component: () => import(/* webpackChunkName: "about" */ '../views/tlias/DeptView.vue')
	  },
	  {
	    path: '/emp',
	    name: 'emp',
	    component: () => import(/* webpackChunkName: "about" */ '../views/tlias/EmpView.vue')
	  }
	]
	```

2. 这里用到的页面跳转换的是整个页面而不是页面中的 **Main** 部分，两个Vue组件的基本布局是一样的，所以<router-link to =""></router-link>需要在每个涉及点击跳转的vue组件中更改

3. 在App.vue动态设置<router-view>展示对应组件

4. 浏览器启动默认访问路径为：`http://localhost:7000/#/`

	所以在index.js下还需要添加` path: '/'`的对象，设置启动默认路径
	
	```javascript
	 {
	    path:"/",
	    redirect:'/dept',
	  }
	```


​	

12. **打包部署**

	- 前端工程打包

		- 通过VS Code的NPM脚本中提供的build按钮来完成

		![image-20240530202817278](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240530202817278.png)

		- 在工程目录下生成一个dist目录，用于存放需要发布的前端资源

	- 通过nginx服务器发布前端工程

		- Nginx是一款轻量级的Web服务器/反向代理服务器及电子邮件（IMAP/POP3）代理服务器。

		- 其特点是占有内存少，并发能力强，在各大型互联网公司都有非常广泛的使用。

		<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240530204236071.png" alt="image-20240530204236071" style="zoom:50%;" />

	- 将前端工程dist目录下得内容拷贝到nginx的html目录下

	- 双击nginx下得nginx.exe文件来启动nginx

	- nginx服务器的端口号是80，所以启动成功之后，我们浏览器直接访问**http://localhost:80** 即

		可，其中80端口可以省略

	- 如果80端口被占用，我们需要通过**conf/nginx.conf**配置文件来修改端口号

		![image-20240530204614320](https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240530204614320.png)

​			可以通过下图命令在**任务管理器**中找到PID为4的进程

<img src="https://2024-2.oss-cn-beijing.aliyuncs.com/typora/image-20240530205125204.png" alt="image-20240530205125204" style="zoom:50%;" />





==从下面就只记录一些项目的小TIPS，具体笔记大纲原资料里都有就不再进行重复==



# Day 4

1. POM： 项目对象模型(Project Object Model）
2. 

