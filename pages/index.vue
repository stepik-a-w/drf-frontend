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

    <h2 class="h1 subtitle">Полезное</h2>
    <b-card-group deck class="items-cards">
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

    <h2 class="h1 subtitle">Сладкое</h2>
    <b-card-group deck class="items-cards">
      <b-card
        title="Название коробочки в пару строк всего"
        img-src="../assets/images/item4.png"
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
        img-src="../assets/images/item5.png"
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
        img-src="../assets/images/item6.png"
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

    <h2 class="h1 subtitle">Новое</h2>
    <b-card-group deck class="items-cards">
      <b-card
        title="Название коробочки в пару строк всего"
        img-src="../assets/images/item1.png"
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
        img-src="../assets/images/item8.png"
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
        img-src="../assets/images/item9.png"
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

    <div class="reviews-head">
      <h2 class="h1 subtitle mr-4 pr-2">Отзывы</h2>
      <b-button variant="dark" size="lg"> 
        <b-icon icon="ArrowRepeat"></b-icon>
        Показать еще
      </b-button>
    </div>
    <b-card-group deck class="reviews-cards mb-5">
      <b-card>
        <b-card-text class="reviews-cards-text">
          Очень качественные и&nbsp;в&nbsp;то&nbsp;же время недорогие вещи. Hse Store учли все наши пожелания и&nbsp;доставили вещи вовремя, спасибо!
        </b-card-text>
        <b-card-text>Вишневский Олег</b-card-text>
      </b-card>
      <b-card>
        <b-card-text class="reviews-cards-text">
          Зарегистрирована на&nbsp;нескольких сайтах и&nbsp;этот тоже не&nbsp;прошла мимо. Оказался одним из&nbsp;лучших. Все просто и&nbsp;гениально. Много заказов, хорошая оплата, легкая регистрация, а&nbsp;главное без вложений.
        </b-card-text>
        <b-card-text>Ильин Алексей</b-card-text>
      </b-card>
    </b-card-group>
  </div>
</template>

<script>
import { BIcon, BIconArrowRepeat } from 'bootstrap-vue' // подключение иконки

export default {
  components: {
    BIcon,
    BIconArrowRepeat
  },

  layout: 'default',

  data() {
    return {
      pagename: "Главная",
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

.subtitle {
  padding-top: 2.2rem;
  margin-bottom: 2.8rem;
  font-size: 37px;
  font-weight: bold;
}

.items-cards {
  .card {
    padding: 0px 15px 15px;
    border: none;
    text-align: center;
    background-color: #F5F5F5;

    img {
      width: 100%;
      max-width: 300px;
    }

    &-body {
      text-align: left;
    }

    &-title {
      font-size: 22px;
      font-weight: 500;
    }
  }

  &-price {
    text-align: right;
    font-size: 27px;
    font-weight: bold;
  }

  .b-form-spinbutton {
    outline: none;
    background-color: #F5F5F5;
    border-color: #6C757D;

    .border-left,
    .border-right {
      border-color: #6C757D!important;
    }

    output {
      color: #6C757D;
      font-weight: bold;
    }
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