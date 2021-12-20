<template>
  <div>
    <h1>WebDev ToDo List</h1>
<div class="user-input">
  <input placeholder="Press enter to add a new todo" v-model="input" @keyup.enter="addItem" ref="input"/>
  <button @click="addItem" class="button is-danger is-large is-rounded addItem">Add Item</button>
  </div>
  <ul v-if="shoppingList">
    <li v-for="(item, i) in shoppingList" :key="i" class="item is-justify-content-space-between"><span class="is-pulled-left">{{ i+1 }} - {{ item }} </span>
    <button class="button is-danger is-small is-rounded deleteItem is-pulled-right" @click="deleteItem(i)">Remove</button></li>
  </ul>
  <button class="button is-danger is-large is-rounded deleteAll" @click="deleteItem()">Delete All</button>
</div>
</template>

<script>
export default {
    name: 'ToDoList',
    data() {
    return {
      input: '',
      shoppingList:[],
      }
    },
    methods: {
    addItem() {
      if (!this.input) return
      this.shoppingList.push(this.input)
      this.input=""
      this.$refs.input.focus()
    },
    deleteItem(i) {
      this.shoppingList = i+1
      ? this.shoppingList.filter((item, x) => x !== i)
      :[]
    }
  },
}
</script>

<style lang="scss" scoped>
input {
   width: 100%;
    padding: 10px 6px;
    margin-right: 10px;
    font-size:2rem;
}

ul {
  display:block;
  margin:0 auto;
  padding:30px;
  border: 1px solid black;
  background-color: white;
  margin-bottom:40px;

  > li {
    color:"black";
    margin-bottom:20px;
    font-size:2rem;
  }
}

h1 {
  font-size:3rem;
  text-decoration: underline;
}
.addItem {
    margin-left:10px;
    margin-right:-20px;
  }
  
  
  .user-input {
    display:flex;
    padding-bottom:20px;
    margin-top:30px;
  }
  .item {
    text-align:left;
    display:flex;
    color:black;
  }
 
  .deleteItem {
      text-transform: uppercase;
     align-self:flex-end;
  }

  .deleteAll {
      margin-bottom: 30px;
  }
</style>

      

 