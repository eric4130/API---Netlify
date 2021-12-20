<template>
<div class="data">
       <h1>Species:</h1>
         <ul>
          <li v-for="(specie, i) in species" :key="i">
            -  {{ specie.name }} 
            </li>
      </ul>
      </div>
</template>

<script>
export default {
    name: 'Species',
    props: {
        species: Array
    }
}
</script>
