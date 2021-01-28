<template>
  <div>
    <b-jumbotron class="item-info mb-2">
      <b-row align-v="center">
        <b-col cols="7">
          <b-img fluid bottom src="../assets/images/item3.png" alt="" width="510"></b-img>
        </b-col>
        <b-col cols="5" class="pl-0">
          <b-link href="/" class="item-info-link">Главная</b-link>
          <h1 class="h1 item-info-title pt-4">Candy Club</h1>
          <p class="item-info-text">I&nbsp;love getting my&nbsp;candy shipment each month! It&nbsp;makes me&nbsp;so&nbsp;happy! Try it! You won&rsquo;t be&nbsp;disappointed</p>
          <div class="item-info-bottom">
            <span class="item-info-price">1290 Р</span><b-button variant="primary" class="ml-4" size="lg">В корзинку</b-button>
          </div>
        </b-col>
      </b-row>
    </b-jumbotron>

    <h2 class="h1 subtitle">Случайные наборы</h2>
    <b-card-group deck class="items-cards mb-5">
      <b-card
        title="Название коробочки в пару строк всего"
        img-src="../assets/images/item3.png"
        img-alt=""
        img-top
        img-width="300">
        <b-row class="pt-3" align-v="center">
          <b-col>
            <b-form-spinbutton id="item-counter" v-model="value_item" min="1" max="100" step="1"></b-form-spinbutton>
          </b-col>
          <b-col class="items-cards-price">
            2650 P
          </b-col>
        </b-row>
      </b-card>
      <b-card
        title="Название коробочки в пару строк всего"
        img-src="../assets/images/item2.png"
        img-alt=""
        img-top
        img-width="300">
        <b-row class="pt-3" align-v="center">
          <b-col>
            <b-button variant="primary">В корзинку</b-button>
          </b-col>
          <b-col class="items-cards-price">
            2650 P
          </b-col>
        </b-row>
      </b-card>
      <b-card
        title="Название коробочки в пару строк всего"
        img-src="../assets/images/item7.png"
        img-alt=""
        img-top
        img-width="300">
        <b-row class="pt-3" align-v="center">
          <b-col>
            <b-button variant="primary">В корзинку</b-button>
          </b-col>
          <b-col class="items-cards-price">
            2650 P
          </b-col>
        </b-row>
      </b-card>
    </b-card-group>
  </div>
</template>

<script>

export default {

  layout: 'default',

  data() {
    return {
      pagename: "Товар",
      value_item: 2
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
.item-info {
  &.jumbotron {
    background-color: #F5F5F5;
  }
  &-link {
    font-size: 18px;
    color: rgba(0,0,0,.5);
    text-decoration: underline;
  }
  &-title {
    padding-bottom: 2rem;
    font-size: 44px;
    font-weight: bold;
  }
  &-text {
    font-size: 21px;
  }
  &-price {
    font-size: 36px;
    font-weight: bold;
  }
  &-bottom {
    display: flex;
    align-items: center;
  }
}

</style>