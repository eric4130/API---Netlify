<template>
  <div id="home-page">
    <h1>WebDev ToDo List</h1>
<div class="user-input">
  <input placeholder="Press enter to add a new todo" v-model="input" @keyup.enter="addItem" ref="input"/>
  <button @click="addItem" class="button is-danger is-large is-rounded additem">Add Item</button>
  </div>
  <ul v-if="shoppingList">
    <li v-for="(item, i) in shoppingList" :key="i" class="item">{{ i+1 }} - {{ item }}</li>
  </ul>
<h1> Welcome to the main page</h1>
<p>The purpose of this page is to show how Vue can connect to an external API, and use it to consume data. The API it's using is called 
  SWAPI and is built off of data from the Star Wars universe. It uses the axios package to connect to the API and then loops through the data and displays 
  specfic attributes in a list fashion.
</p>
<p id="message"></p>
<button class="button is-link is-large is-rounded bigbutton event">Click Here</button>

</div>
</template>


<script>
export default {
  name: 'Home',
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
    }
  },
  mounted() {
    document.title = "Home  || API-Netlify"

    function newText() {
         document.querySelector("#message").textContent =  "See our ToDo List above to brainstorm your development process !!";
    }

    document.querySelector('.event').addEventListener('click', newText);

  },
}


</script>

<style lang="scss" scoped>

h1 {
  font-size:3rem;
  text-decoration: underline;
}

p {
  font-size:2rem;
  margin-top:20px;
}

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
</style>
