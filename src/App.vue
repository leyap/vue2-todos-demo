<template>
  <div id="app">
    <h1>{{title}}</h1>
    <ul>
    <li v-for= "(todo,index) in todos" :id='index'>
    <label>{{index+1}}.{{todo.value}}</label>
    </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
	title: "vue-todos",
	       todos: [
	       {value:"read one book for develop", done: false},
	       {value:"something add", done: true},
	       {value:"write note", done: false}
	       ]
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  //font-size: 30px;
}

h1, h2 {
  font-weight: normal;
}
ul {
	/*text-align: left;*/
	width: 50%;
	border: 1px solid #444;
	padding: 0px;
	margin: 0 auto;
}

ul li {
	list-style: none;
		padding: 10px;
}
ul li:not(:last-child){
	border-bottom: 1px solid #444;
}
ul li:last-child {
 }
</style>
