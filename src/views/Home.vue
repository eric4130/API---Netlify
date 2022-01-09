<template>
  <div id="home-page">
<h1> Welcome to the Home page</h1>
<p>The purpose of this page is to show how Vue can make Javascript events easier to understand and read.  The Todo List (imported as a child component) utilizes some basic 
  Vue directives and methods to accomplish dynamic list management. The input shows an example of v-model 2-way data binding. The 2 Big Buttons are used to show some basic DOM manipulation. The first, in vanilla JS,
  executes a function based on the 'click' event. The second button accomplishes the same goal, but with the help of Vue directives and methods.
</p>
 <ToDoList />
<h2> Type something in the input below </h2>
<p id="input">{{ reactiveinput }}</p>
<input v-model="reactiveinput">

<!-- vanilla JS event listener -->
<p id="message"></p>
<button class="button is-link is-large is-rounded bigbutton js-event">Click Here</button>

<!-- Vue event listener -->
  <p>{{ message2 }}</p>
  <button class="button is-link is-large is-rounded bigbutton vue-event" v-on:click = "displayMessage">Click Here</button>
  
<!-- Methods -->
 <p>{{ message3 }}</p>
  <button class="button is-link is-large is-rounded bigbutton" v-on:click = "reverseMessage">Click Here</button>
  <p>{{ reversedMessage }}</p>


</div>
</template>


<script>
import ToDoList from '../components/ToDoList'
export default {
  name: 'Home',
  components: {
    ToDoList
  },
  data() {
    return {
      reactiveinput: "",
      message2:'',
      message3: 'This line shows how methods work. After clicking the button, JS methods are used to slice, reverse and join.'
    }
  },
  /* in mounted() is where you can write vanilla JS */
  mounted() {
    document.title = "Home  || API-Netlify"
/* vanilla js event */
    function newText() {
        
         let message1 = document.querySelector("#message").textContent;
      if (message1 == '') {
         document.querySelector("#message").textContent =  "This is a traditional Javascript event listener";
        document.querySelector('.js-event').style.backgroundColor='red';
        document.querySelector(".js-event").textContent = "Vanilla JS";
      } else {
        document.querySelector("#message").textContent = "";
        document.querySelector('.js-event').style.backgroundColor='';
        document.querySelector(".js-event").textContent = "Click Here";
          }
      }

    document.querySelector('.js-event').addEventListener('click', newText);

  },

  methods: {
/* vue.js events */
    displayMessage() {
      if (this.message2 == '') {
      this.message2 = "This is the way Vue does event listeners!";
      document.querySelector('.vue-event').style.backgroundColor='red';
      document.querySelector(".vue-event").textContent = "Vue.JS";
      } else {
        this.message2 = '';
        document.querySelector('.vue-event').style.backgroundColor='';
       document.querySelector(".vue-event").textContent = "Click here";
      }
     
    },
    reverseMessage() {
      this.message3 = this.message3.split('').reverse().join('');
    }
  },
  computed: {
    reversedMessage: function() {
      return this.message3.split('').reverse().join('');
    }
  }
}


</script>

<style lang="scss" scoped>

h1 {
  font-family: 'Caesar Dressing', cursive;
  font-size:2rem;
  text-decoration: underline;
}

p {
  font-family: 'Revalia', cursive;
  font-size:2rem;
  margin-top:20px;
}

p#input {
  font-size:3rem;
}

input {
  margin-top:20px;
}

h2 {
  padding-top:20px;
}

</style>
