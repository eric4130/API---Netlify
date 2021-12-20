<template>
<div class="data">
  <h1>Films:</h1>
      <ul>
          <li v-for="(film, i) in films" :key="i">
             - {{ film.title }}
            </li>
      </ul>
      </div>
</template>

<script>
export default {
    name: 'Films',
    props: {
        films: Array
    }
}
</script>
