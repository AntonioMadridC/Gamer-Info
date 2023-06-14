<template>
  <div>
    <nav class="navbar navbar-expand-lg text-white p-3 bg-dark" data-bs-theme="dark">
      <div class="container-fluid">
        <h4><i class="bi bi-headset"></i> Games opinion</h4>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNavAltMarkup"
          aria-controls="navbarNavAltMarkup"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
          <div class="navbar-nav">
            <router-link class="px-2" to="/"
              ><i class="bi bi-house-fill"></i> Home</router-link
            >
            | <router-link class="px-2" to="/juegos">Juegos</router-link>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "my-nav",
  // props: {},
  data: function () {
    return {};
  },
  // computed: {},
  //methods: {}
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
};
</script>

<style scoped>
</style>