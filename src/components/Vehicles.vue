<template>
<div class="data">
      <h1>Vehicles:</h1>
         <ul>
          <li v-for="(vehicle, i) in vehicles" :key="i">
             - {{ vehicle.name }} 
            </li>
      </ul>
      </div>
</template>

<script>
export default {
    name: 'Vehicles',
    props: {
        vehicles: Array
    }
}
</script>
