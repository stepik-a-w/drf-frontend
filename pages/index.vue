<template>
  <div>
    <b-jumbotron class="promo mb-2 pb-0">
      <b-row align-v="center">
        <b-col cols="7" class="pl-5 pr-3 pb-3 ">
          <h1 class="h1 promo-title pb-4">Коробочки с&nbsp;вкусностями!</h1>
          <p class="promo-text pb-3">Купите набор в&nbsp;онлайн-магазине с&nbsp;доставкой или закажите подписку на&nbsp;набор каждую недели, раз в&nbsp;две недели или месяц</p>
          <b-badge variant="primary" class="promo-price">от 999 Р</b-badge>
        </b-col>
        <b-col cols="5" class="pl-0">
          <b-img fluid bottom src="../assets/images/item10.png" alt="" width="510"></b-img>
        </b-col>
      </b-row>
    </b-jumbotron>

    <b-card-group v-for="item in items" deck class="items-cards">

      <card :id="item.id" :img="item.image" :title="item.title" :price="item.price" />

    </b-card-group>

  </div>
</template>

<script>
import { BIcon, BIconArrowRepeat } from 'bootstrap-vue' // подключение иконки


export default {

  components: {
    BIcon,
    BIconArrowRepeat,
  },

  layout: 'default',

  data() {
    return {
      items: [],
      pagename: "Главная",
      value_item: 2,
      host: "http://127.0.0.1:8000/api/v1",
    }
  },

    methods: {

        loadData: function() {
            this.$axios.$get(this.host+'/items').then((result) => {
                this.items = result.results;
                console.log(this.items)
                console.log("Данные загружены")
            })
        }

    },

  created() {

      var token = this.$auth.$storage.getLocalStorage("token");

      this.$axios.setToken('Token'+" "+token);

      this.loadData();

  },

}
</script>

<style lang="scss">
.promo {
  &.jumbotron {
    background-color: #F5F5F5;
  }
  &-title {
    font-size: 36px;
    font-weight: bold;
  }
  &-text {
    font-size: 27px;
  }
  &-price {
    padding: .75rem 1rem;
    font-size: 27px;
  }
}
.reviews-head {
  display: flex;
  align-items: center;
  padding-top: 1rem; 
  padding-bottom: .55rem; 
}
.reviews-cards {
  .card {
    position: relative;
    padding: 10px 12px 8px;
    padding-right: 50px;
    border: none;
    background-color: #F5F5F5;
    

    &::after {
      position: absolute;
      top: 29px;
      right: 27px;
      content: '';
      width: 40px;
      height: 40px;
      background:  url('../assets/images/quotes.svg') right top no-repeat;
      background-size: 40px 40px;
    }
  }

  &-text {
    font-style: italic;
  }
}
</style>