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

    <ul>
      <li v-for="dope in dopes" v-bind:key="dope.id">
        {{dope.name}}
      </li>
    </ul>

    <ul>
      <li v-for="(todo, index) in todos" v-bind:key="todo.id"
          :class="{'isFinished':todo.finished}">
        <input type="checkbox" :checked="todos.finished" />
        {{++index}}, {{todo.name}}
        <a v-bind:href="'?id=4'+todo.id" >zeigen</a>
      </li>
    </ul>

    <button v-on:click="test">Allertbotton</button>

  </div>
</template>

<script>


export default {
  name: 'App',
  data: () => ({
    welcome: 'welcome @ your easy dealer',
    name: 'Ganja Shop 4 chillibilly',
    dopes: [
      {id: 1, name: "White Widow"},
      {id: 2, name: "Purple Hase"},
      {id: 3, name: "orange Butt"},
      {id: 4, name: "...skunk..."},
    ],
    todos: [
      {id: 1, finished: false, name: "authentifizieren"},
      {id: 2, finished: false, name: "ganja Wählen"},
      {id: 3, finished: false, name: "mehr ganja Wählen"},
      {id: 4, finished: false, name: "bestellung bestätigen"},
    ]
  }),
  methods: {
    test() {
      alert("Hellau");
    }
  }
}
</script>

<style>
.isFinished {
  text-decoration: line-through;
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
  -moz-osx-font-smoothing: grayscale;
  font-size: 100%;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
  margin-bottom: 5px;
}
</style>
