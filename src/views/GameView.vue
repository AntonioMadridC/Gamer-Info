<template>
  <div>
    <GameDisplay :id="id" class="mt-5" ></GameDisplay>
  </div>
</template>

<script>
import GameDisplay from '../components/GameDisplay.vue'

export default {
  name: 'GameView',
  props:{
    id:{
        type:String,
        required:true
    }},
  components: {
    GameDisplay
  }
}
</script>