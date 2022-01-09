<template>
    <div id="api-page">
      <h1> Welcome to the API page</h1>
<p>The purpose of this page is to show how Vue can connect to an external API, and use it to consume data. The API it's using is called 
  SWAPI and is built off of data from the Star Wars universe. It uses the axios package to connect to the API and then loops through the data and displays 
  specfic attributes in a list fashion. Bulma, a CSS library, combined with SCSS is used to style the grid and make it responsive.
</p>
      <div class="columns is-tablet">
             <div class="column">
                 <div class="box">
                    <Films
                      v-bind:key = "films.id"
                      v-bind:films="films" />
                  </div>
              </div>
              <div class="column">
                   <div class="box">
                        <People
                      v-bind:key = "people.id"
                      v-bind:people="people" />
                   </div>
              </div>
              <div class="column">
                   <div class="box">
                        <Planets
                      v-bind:key = "planets.id"
                      v-bind:planets="planets" />
                   </div>
              </div>
      </div>
      <hr>
      <div class="columns is-tablet" id="bottom">
          <div class="column">
              <div class="box">
                    <Species
                  v-bind:key = "species.id"
                  v-bind:species="species" />
              </div>
          </div>
          <div class="column">
             <div class="box">
                    <Starships
                  v-bind:key = "starships.id"
                  v-bind:starships="starships" />
              </div>
           </div>
          <div class="column">
               <div class="box">
                  <Vehicles 
                  v-bind:key = "vehicles.id"
                  v-bind:vehicles="vehicles" />
                </div>
          </div>
      </div>
</div>
</template>
    
<script>
import axios from 'axios'
import Films from '../components/Films'
import People from '../components/People'
import Planets from '../components/Planets'
import Species from '../components/Species'
import Starships from '../components/Starships'
import Vehicles from '../components/Vehicles'

export default {
  name: 'API',
  components: {
    Films,
    People,
    Planets,
    Species,
    Starships,
    Vehicles
  },
  data() {
    return {
      films: [],
      people:[],
      planets:[],
      species:[],
      starships:[],
      vehicles:[]
    }
  },
  mounted() {
    this.getSWAPI()
    document.title = "Star Wars API  || API-Netlify"
  },
  methods: {
    async getSWAPI() {
    await axios
    .get('/films/', '/people/', '/planets/', '/species/','/starships/','/vehicles/')
    .then(response => {
      this.films = response.data;
      this.people = response.data;
      this.planets = response.data;
      this.species = response.data;
      this.starships = response.data;
      this.vehicles = response.data;
    })
    .catch(error => {
      console.error(error);
    })
    }
  }
}
</script>

<style scoped>

h1 {
font-family: 'Caesar Dressing', cursive;
  font-size:2rem;
  text-decoration: underline;
}

p {
  font-family: 'Revalia', cursive;
  font-size:2rem;
  margin-top:20px;
   margin-bottom:10px;
}

.box {
  background-color: #00000000;
  color:white;
  margin:10px 0px 0px;
  padding:0px 0px 10px;
}

</style>
