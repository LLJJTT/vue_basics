<template>
	<div class="test">
		<!-- 获取数据 -->
		<!-- 用双重花括号，获取data中的值 -->
		<h1>{{title}}</h1>
		<p>{{user.firstname}}</p>

		<!-- 用v-text获取data中user的值 -->
		<p v-text="user.lastname"></p>
		<!-- v-if -->
		<p v-if="showName">{{user.firstname}}</p>
		<!-- v-else -->
		<p v-else="showName">nobody</p>
		<!-- v-for -->
		<ul>
			<!-- 随便起名字 -->
			<li v-for="suibianqi in items">{{suibianqi.title}}</li>
		</ul>
		<!-- v-on -->
		<button v-on:click="hello('helloeverybody')">Say hello</button>
		<!-- 键盘事件 -->
		<input type="text" v-on:keyup="keypress">
		<input type="text" v-on:keyup.enter="enterpress">
		<hr>
		<!-- computed 计算属性 -->
		<label>FirstName:</label>
		<input type="text" v-model="user.firstname">
		<br>
		<label>LastName:</label>
		<input type="text" v-model="user.lastname">
		<br>
		<h3>{{fullname}}</h3>
		<!-- props 属性 -->
		<h2>{{msg}}</h2>
	</div>
</template>

<script>
// 让外部文件能引入这个组件
	export default{ 
		// 文件名字叫啥，name就是傻，一般小写 
		name:"test",
		props:{
			msg:{
				type:String,
				default:"默认就是当前文字"
			}
		},
		data(){
			return{
				title :"hello vue.js!",
				user :{
					firstname :"zhangsan",
					lastname :"lisi"
				},
				showName:false,
				items:[
					{title:"item 1"},
					{title:"item 2"},
					{title:"item 3"}
				]
			}
		},
		methods:{
			hello:function(greeting){
				alert(greeting);
			},
			keypress:function(){
				console.log("1213131");
			},
			enterpress:() =>{
				alert(1);
			}
		},
		computed:{
			fullname:function(){
				return this.user.firstname + "  " +this.user.lastname;
			}
		}

	}
</script>

<style scoped>
/*scoped 样式划分区域*/
	
</style>





