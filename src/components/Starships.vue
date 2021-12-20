<template>
<div class="data">
      <h1>Starships:</h1>
         <ul>
          <li v-for="(ship, i) in starships" :key="i">
             - {{ ship.name }} 
            </li>
      </ul>
      </div>
</template>

<script>
export default {
    name: 'Starships',
    props: {
        starships: Array
    }
}
</script>
