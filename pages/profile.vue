<template>
  <div>
    <b-row class="pb-5">
      <b-col cols="8">
        <h1 class="h3 mb-5">История заказов</h1>
        <b-card no-body class="mb-4">
          <b-list-group flush>
            <b-list-group-item class="px-4 py-3">
              <b-row class="order-bar">
              <b-col class="order-number" cols="3"># 45353544</b-col>
              <b-col class="order-date" cols="4">21 декабря 14:05</b-col>
              <b-col class="order-price">5 900 Р</b-col>
              <b-col class="order-status"><b-badge variant="success">Выполняется</b-badge></b-col>
            </b-row>
            </b-list-group-item>
            <b-list-group-item class="text-muted">Товарная позиция 1, Товарная позиция 2, Товарная позиция 3</b-list-group-item>
          </b-list-group>
        </b-card>
        <b-card no-body class="mb-4">
          <b-list-group flush>
            <b-list-group-item class="px-4 py-3">
              <b-row class="order-bar">
              <b-col class="order-number" cols="3"># 453532343</b-col>
              <b-col class="order-date" cols="4">18 декабря 21:17</b-col>
              <b-col class="order-price">3 700 Р</b-col>
              <b-col class="order-status"><b-badge variant="success">Выполнен</b-badge></b-col>
            </b-row>
            </b-list-group-item>
          </b-list-group>
        </b-card>
        <b-card no-body class="mb-4">
          <b-list-group flush>
            <b-list-group-item class="px-4 py-3">
              <b-row class="order-bar">
              <b-col class="order-number" cols="3"># 453514299</b-col>
              <b-col class="order-date" cols="4">12 декабря 18:17</b-col>
              <b-col class="order-price">16 300 Р</b-col>
              <b-col class="order-status"><b-badge variant="warning">Отменен</b-badge></b-col>
            </b-row>
            </b-list-group-item>
          </b-list-group>
        </b-card>
      </b-col>
      <b-col cols="4">
        <h2 class="h3 mb-5">Профиль</h2>
        <b-form class="profile-form px-4">


          <b-form-group
            id="fieldset-1"
            label="Почта:"
            label-for="input-1"
          >
            <b-form-input id="input-1" v-model="email" trim></b-form-input>
          </b-form-group>


          <b-form-group
            id="fieldset-2"
            label="Имя:"
            label-for="input-2"
          >
            <b-form-input id="input-2" v-model="first_name" trim></b-form-input>
          </b-form-group>


          <b-form-group
            id="fieldset-3"
            label="Фамилия:"
            label-for="input-3"
          >
            <b-form-input id="input-3" v-model="last_name" trim></b-form-input>
          </b-form-group>


          <b-form-group
            id="fieldset-4"
            label="Телефон:"
            label-for="input-4"
          ><b-form-input id="input-4" trim></b-form-input>

          </b-form-group>

          <b-button type="submit" variant="primary" size="lg" class="mt-3">Сохранить</b-button>
        </b-form>
      </b-col>
    </b-row>
  </div>
</template>

<script>

export default {

  layout: 'default',

  data() {
    return {

      email: this.$store.state.user.email,
      first_name: this.$store.state.user.first_name,
      last_name: this.$store.state.user.last_name,

    }
  },

  // тестовый запрос для демонстрации возможностей

  async asyncData({ $axios }) {

    //

  },

  methods: {

    loadData: function() {

        this.$store.dispatch('fetch_user');

    }
  },

  created() {

        this.loadData();

  },

}
</script>

<style lang="scss">
.order {
  &-bar {
    font-size: 18px;
    line-height: 24px;

    .col {
      padding-left: 10px;
      padding-right: 10px;
    }
  }
  &-number,
  &-date,
  &-price {
    font-weight: bold;
  }
  &-number {
    color: #1B76EA;
  }
  &-price {
    text-align: center;
  }
  &-status {
    text-align: right;
    .badge {
      font-size: 18px;
      font-weight: 500;

      &.badge-warning {
        color:#fff;
      }
    }
  }
}

.profile-form {
  padding-top: 2rem;
  padding-bottom: 2rem;
  background-color: #F5F5F5;
  border-radius: 4px;

  label {
    padding-bottom: 5px;
  }
}
</style>