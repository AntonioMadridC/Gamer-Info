<template>
  <div class="container">
    <div class="card" style="max-width: 1200px">
      <div class="row g-0">
        <div class="col-md-5">
          <img
            :src="game.background_image"
            class="img-fluid rounded-start"
            alt="..."
          />
        </div>
        <div class="col-md-7">
          <div class="card-body">
            <h5 class="card-title">{{ game.name }}</h5>
            <ul class="list-group list-group-flush">
              <li class="list-group-item">Puntaje: {{ game.rating }}/5</li>
              <li class="list-group-item">
                Clasificación ESRB: {{ game.esrb_rating.name }}
              </li>
              <li class="list-group-item">Sitio: <a :href="game.website">{{game.website}}</a></li>
            </ul>
            <p class="card-text" v-html="game.description">
            </p>
            <p class="card-text">
              <small class="text-body-secondary"
                >Fecha de lanzamiento: {{ game.released }}</small
              >
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "component-name",
  props: {
    id:{
        type:String,
        required:true
    }
  },
  data: function () {
    return {
      game: {
        name: "",
        released: "",
        esrb_rating: {},
        rating: "",
        background_image: "",
        description: "",
        website: "",
      },
    };
  },
  // computed: {},
  methods: {
    getGame() {
      axios
        .get(
          `https://api.rawg.io/api/games/${this.id}?key=a3d2d06dd519445db789457635c79265`
        )
        .then((result) => {
          let game = result.data;
          console.log(result);
          if (game.esrb_rating == null) {
            game.esrb_rating = { name: "indefinida" };
          }
          this.game = game;
        });
    },
  },
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  created(){
    this.getGame()
  }
  // -- End Lifecycle Methods
};
</script>

<style scoped>
</style>