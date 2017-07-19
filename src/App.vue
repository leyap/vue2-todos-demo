<template>
  <div id="app">
    <h1>{{title}}</h1>
    <ul>
    <li v-for= "(todo,index) in todos" :id='index' :class="{'checked': todo.done}">
    <label>{{index+1}}.{{todo.value}}</label>
      <time> {{todo.created | date}}</time>
    </li>
    </ul>
  </div>
</template>

<script>
  import moment from 'moment'
  import 'moment/locale/zh-cn'
  moment.locale('zh-ch');
export default {
  name: 'app',
  filters: {
    date(val) {
      return moment().calendar()
    }
  },
  data () {
    return {
        title: "vue-todos",
	    todos: [
	       {value:"read one book for develop", done: false, created: Date.now()},
	       {value:"something add", done: true, created: Date.now()+30000},
	       {value:"write note", done: false, created: Date.now()-300000}
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
	text-align: left;
	width: 50%;
	border: 1px solid rgba(100, 100, 100, 0.5);
	padding: 0px;
	margin: 0 auto;
    padding: 0 20px;
  position: relative;
}

ul li {
  list-style: none;
  padding: 10px;
}
ul .checked {
    color: rgba(100, 100, 100, 0.7);
  text-decoration: line-through;
}

ul li label {
  position: relative;
  left: 20px;
  right: 20px;
  height: 100%;
}
ul li time {
  /*margin-left: 20px;*/
  position: absolute;
  right: 20px;
  font-size: 10px;
}
ul li:not(:last-child) {
  border-bottom: 1px dashed rgba(100, 100, 100, 0.3);
}
ul li:last-child {
}
</style>
