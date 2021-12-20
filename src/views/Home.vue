<template>
  <div id="home-page">
  <ToDoList />
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
import ToDoList from '../components/ToDoList'
export default {
  name: 'Home',
  components: {
    ToDoList
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

<style scoped>

h1 {
  font-size:3rem;
  text-decoration: underline;
}

p {
  font-size:2rem;
  margin-top:20px;
}

</style>
