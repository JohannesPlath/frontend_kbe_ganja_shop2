<template>
  <div id = "app" >
    <div class="greenBox">
      {{welcome}}
    </div>
    <div class="greenBox" style=" font-family: Arial, Helvetica, sans-serif;
         font-size: 150%;" >
      {{name}}
    </div>
    <hr>

    <main_products class="mainProducts"/>

    <ul>
      <li v-for="(todo, index) in todos" v-bind:key="todo.id"
          :class="{'isFinished':todo.finished}">
        <input type="checkbox" :checked="todos.finished" />
        {{++index}}.  {{todo.name}}
        <a v-bind:href="'?id='+todo.id" >zeigen</a>
      </li>
    </ul>

    <button v-on:click="test">Allertbotton</button>





  </div>
</template>

<script>
import main_products from "@/components/MainProductList";

export default {
  name: 'App',
  data: () => ({
    welcome: 'welcome @ your easy dealer',
    name: 'Ganja Shop 4 chillibilly',

    todos: [
      {id: 1, finished: true, name: "authentifizieren"},
      {id: 2, finished: false, name: "ganja Wählen"},
      {id: 3, finished: true, name: "mehr ganja Wählen"},
      {id: 4, finished: false, name: "bestellung bestätigen"},
    ]
  }),
  methods: {
    test() {
      alert("Hellau");
    }
  },
  components:{
    main_products,
  }
}
</script>

<style>
.isFinished {
  text-decoration: line-through;
}
.mainProducts{
  flex-direction: row;
}
.greenBox {
  border: 10px solid burlywood;
  webkit-border-radius: 14px 14px 14px 14px;
  border-radius: 14px 14px 14px 14px;
  background-color: antiquewhite;
  margin: 5px;
  font-size: 150%;
  padding: 10px;
  margin-left: 30%;
  margin-right: 30%;
}
#app {
  background: gray;
  display: flex;
  flex-direction: column;
  justify-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: auto;
  font-size: 100%;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
  margin-bottom: 5px;
}
</style>
