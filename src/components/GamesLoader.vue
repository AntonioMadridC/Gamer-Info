<template>
  <div>
    <h1>Juegos</h1>
    
    <div class="containerGames">
      <div
        v-for="(game, index) in games"
        :key="index"
        class="card"
        style="width: 18rem"
      >
        <img
          :src="game.background_image"
          class="card-img-top"
          alt="imagen de juego"
        />
        <div class="card-body">
          <h5 class="card-title">{{ game.name }}</h5>
        </div>
        <ul class="list-group list-group-flush">
          <li class="list-group-item">Puntaje: {{ game.rating }}/5</li>
          <li class="list-group-item">
            Clasificación ESRB: {{ game.esrb_rating.name }}
          </li>
          <li class="list-group-item">
            Fecha de estreno (aaaa-mm-dd): {{ game.released }}
          </li>
        </ul>
        <div class="card-body">
          <button class="btn btn-primary" @click="redirect(game.slug)">
            Más detalles
          </button>
        </div>
      </div>
    </div>
    <button @click="getData" class="btn btn-warning my-3">Mostrar Juegos</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "games-loader",
  // props: {},
  data: function () {
    return {
      games: [],
      page: 1,
    };
  },
  computed: {
    gamesFilter() {
      return this.games.filter((i) => i.esrb_rating !== null);
    },
  },
  methods: {
    getData() {
      axios
        .get(
          `https://api.rawg.io/api/games?key=a3d2d06dd519445db789457635c79265&page=${this.page}&page_size=9&genres=indie`
        )
        .then((json) => {
          console.log(json);
          let results = json.data.results;
          console.log(results);
          results.forEach((game) => {
            if (game.esrb_rating == null) {
              game.esrb_rating = { name: "indefinida" };
            }
            this.games.push(game);
          });
          console.log(this.games);
          this.page++;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    redirect(id) {
      let index = id;
      this.$router.push(`/juegos/${index}`);
    },
  },
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
};
</script>

<style scoped>
.containerGames {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  width: 90%;
  margin: 0 auto;
  gap: 16px;
}
</style>