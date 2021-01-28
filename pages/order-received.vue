<template>
  <div>
    <b-row align-v="center" align-h="center" class="order-info">
      <b-col cols="8">
        <b-jumbotron class="order-info-card">
          <b-img src="../assets/images/item10.png" alt="" width="200"></b-img>
          <h1 class="h1 order-info-title">Заказ отправлен</h1>
          <p class="order-info-text">Скоро мы вам перезвоним, чтобы подтвердить его</p>
          <b-button variant="primary" size="lg">Перейти к истории заказов</b-button>
        </b-jumbotron>
      </b-col>
    </b-row>
  </div>
</template>

<script>

export default {

  layout: 'default',

  data() {
    return {
      pagename: "Заказ отправлен"
    }
  },

  // тестовый запрос для демонстрации возможностей

  async asyncData({ $axios }) {

    let planet = await $axios.$get('https://swapi.dev/api/planets/1');
    console.log(planet)
    return { planet }

  },

  methods: {
    loadData: function() {
      this.$axios.$get('https://swapi.dev/api/planets/2').then((result) => {
        console.log(result)
      })

    }
  }

}
</script>

<style lang="scss">
.order-info {
  margin-top: 7.8rem;
  margin-bottom: 7.8rem;

  &-card {
    padding-top: 3.1rem;

    text-align: center;
  }

  &-title {
    padding-top: 0.5rem;
    padding-bottom: 0.2rem;
    font-size: 45px;
  }
  &-text {
    max-width: 300px;
    margin: 0 auto 1.4rem;
    font-size: 22px;
    line-height: 1.3;
  }
}
</style>