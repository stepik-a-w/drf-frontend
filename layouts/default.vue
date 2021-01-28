<template>
  <div>
    <b-container>
      <heading />
      <Nuxt />
      <footing />
    </b-container>
  </div>
</template>

<script>
import heading from "~/components/heading.vue";
import footing from "~/components/footing.vue";

export default {
  components: {
    heading,
    footing
  }
};
</script>

<style lang="scss">
/*

  Здесь стили для основного лэйаута

  */
</style>