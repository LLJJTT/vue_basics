<template>
	<div class="users">
		<h1>Users</h1>
		<!-- 添加用户信息 -->
		<form v-on:submit="addUser">
			<input type="text" v-model="newUser.name" placeholder="EnterMe"> 
			<input type="text" v-model="newUser.email" placeholder="EnterMe"> 
			<input type="submit" value="Submit">
		</form>
		<!-- 展示用户信息 -->
		<ul>
			<li v-for="qq in users">
				<input type="checkbox" v-model="qq.contacted" class="toggle">
				<span :class="{contacted:qq.contacted}">
					{{qq.name}}:{{qq.email}}
					<button v-on:click="deleteuser(qq)">x</button>
				</span>
			
		</li>
		</ul>
	</div>
</template>

<script>
// 让外部文件能引入这个组件
	export default{ 
		// 文件名字叫啥，name就是傻，一般小写 
		name:"users",
		data(){
			return{
				newUser:{},
				users:[
					{
						name:"zhangsan",
						email:"heloawda@qq.com",
						contacted:false 
					},
					{
						name:"li",
						email:"awda@qq.com",
						contacted:false 
					},
					{
						name:"wangwu",
						email:"kdsnf@qq.com",
						contacted:false 
					}
					
				]
			}
		},
		methods:{
			addUser:function(e){
				// console.log(1);
				this.users.push({
					name:this.newUser.name,
					email:this.newUser.email,
					contacted:false
				})
				e.preventDefault();

			},
			deleteuser:function(qq){
					this.users.splice(this.users.indexOf(qq),1);
			}
		},
	}
</script>

<style scoped>
/*scoped 样式划分区域*/
	.contacted{
		text-decoration: line-through;
	}
</style>





