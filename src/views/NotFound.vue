<template>
  <div>
    <h1>La página que buscas no existe</h1>
    <h1><router-link to="/">home</router-link></h1>
    <ErrorBanner></ErrorBanner>
    
  </div>
</template>

<script>
import ErrorBanner from "@/components/ErrorBanner.vue";
export default {
  name: "NotFound",
  components: {
    ErrorBanner
  },
};
</script>