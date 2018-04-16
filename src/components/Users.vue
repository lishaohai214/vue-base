<template>
  <div class="users">
      <h1>hello User </h1>
      <ul>
      	<li v-on:click="user.show = !user.show" v-for="user in users">
      		<h2>{{user.name}}</h2>
      		<!-- <h3 v-if="user.show">{{ user.position }}</h3> -->
      		<h3>{{ user.email }}</h3>
      	</li>
      </ul>
      <button @click="deleteUser">删除</button>
  </div>
</template>

<script>



export default {
  name: 'users',
  // props:["users"],
  props:{
  	"users":{
  		type: Array,
  		require: true
  	}
  },
  data () {
    return {
    	
    }
  },
  methods:{
  	deleteUser(){
  		// 在后面删除一个元素
  		this.users.pop() 
  	}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .users{
  	width: 100%;
  	max-width: 1200px;
  	margin: 40px auto;
  	padding: 0 20px;
  	box-sizing: border-box;

  }
  ul{
  	display: flex;
  	flex-wrap: wrap;
  	list-style-type: none;
  }
  ul > li {
  	flex-grow: 1;
  	flex-basis: 200px;
  	text-align: center;
  	padding: 30px;
  	margin: 10px;
  	border: 1px solid #222;
  }
</style>
