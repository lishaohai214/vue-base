<template>
  <div class="home">
      <app-header v-on:changedTitle="updateTitle($event)" v-bind:title="title"></app-header>
      <Users :users="users"></Users>
      <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>

import Header from './Header'
import Users from './Users'
import Footer from './Footer'

export default {
  name: 'home',
  data () {
    return {
    	title:'home传过来的title',
    	users:[
    		// { name:"henry", position:"web前端开发",show:false},
    		// { name:"bucky", position:"web前端开发",show:false},
    		// { name:"emily", position:"web前端开发",show:false},
    		// { name:"easy", position:"web前端开发",show:false},
    		// { name:"heily", position:"web前端开发",show:false},
    		// { name:"sheldon", position:"web前端开发",show:false},
    		// { name:"macroks", position:"web前端开发",show:false},
    	]
    }
  },
  components:{
	"app-header": Header,
	"Users": Users,
	"app-footer": Footer
  },
  methods:{
  	updateTitle(title){
  		this.title = title;
  	}	
  },
  created(){
  		this.$http.get("http://jsonplaceholder.typicode.com/users")
  		.then(data=>{
  			// console.log(data);
  			this.users = data.body;
  		})
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
</style>
