<template>
<div class="data">
      <h1>People:</h1>
         <ul>
          <li v-for="(person, i) in people" :key="i">
             - {{ person.name }} 
            </li>
      </ul>
      </div>
</template>

<script>
export default {
    name: 'People',
    props: {
        people: Array
    }
}
</script>
