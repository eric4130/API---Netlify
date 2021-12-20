<template>
<div class="data">
       <h1>Planets:</h1>
         <ul>
          <li v-for="(planet, i) in planets" :key="i">
             - {{ planet.name }} 
            </li>
      </ul>
      </div>
</template>

<script>
export default {
    name: 'Planets',
    props: {
        planets: Array
    }
}
</script>
