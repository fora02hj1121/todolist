<template>
  <div id="app">
	<HelloWorld :prop="hello" @hello="childCall" />	
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'HelloWorld',
  props:['prop'],
  components:{
		
	},
  data: function() {
	  name:"HelloWorld"
	  
	  return{
		 hello:"a", 
	  }    
  },
 methods:{	
	emitCall(){
		this.$emit('hello','b');
	},
	 childCall(val){
		 console.log(val);
		 this.hello=val;
	 }
	
 },
 computed:{
	reverseMessage:function(){
		return this.message.split('').reverse().join('');
	} 
	
 },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
a {
  color: #42b983;
}
.name{
	background-color:red;	
}
.red{
	background-color:red;	
}
.blue{
	background-color:blue;	
}
.green{
	background-color:green;	
}
</style>
