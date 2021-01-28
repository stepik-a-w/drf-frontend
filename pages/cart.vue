<template>
  <div>
    <h1 class="h1 mb-4 cart-title">Корзина</h1>
    <b-row class="pb-5">
      <b-col cols="8">
        <b-row class="items-cards">
          <b-col cols="6">
            <b-card
              class="mb-3"
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
          </b-col>
          <b-col cols="6">
            <b-card 
              class="mb-3"
              title="Название коробочки в пару строк всего" 
              img-src="../assets/images/item2.png" 
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
          </b-col>
          <b-col cols="6">
            <b-card 
              class="mb-3"
              title="Название коробочки в пару строк всего" 
              img-src="../assets/images/item7.png" 
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
          </b-col>
          <b-col cols="6">
            <b-card 
            class="mb-3"
            title="Название коробочки в пару строк всего" 
            img-src="../assets/images/item7.png" 
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
          </b-col>
        </b-row>
      </b-col>
      <b-col cols="4">
        <b-form @submit="onSubmit" @reset="onReset" class="cart-form ">
          <div class="px-4">
            <b-form-group class="mb-1">
              <p class="cart-form-info"><b>Всего коробочек:</b> 5</p>
            </b-form-group>
            <b-form-group>
              <p class="cart-form-info"><b>Общая сумма:</b> 6420 Р</p>
            </b-form-group>
            <b-form-group
              class="mb-4"
              label="Адрес доставки:"
              label-for="textarea"
              :invalid-feedback="invalidFeedback"
              :state="state"
            >
               <b-form-textarea
                id="textarea"
                v-model="text"
                rows="5"
                max-rows="7"
              ></b-form-textarea>
            </b-form-group>
            <b-form-group class="mb-1">
              <p class="cart-form-label">Дата доставки:</p>
              <div class="cart-form-date mb-2">
                <b-form-select
                  v-model="selected" :options="options">
                  <b-form-select-option value="30">Завтра 30 января</b-form-select-option>
                  <b-form-select-option value="29">Сегодня</b-form-select-option>
                  <b-form-select-option value="week">Через неделю</b-form-select-option>
                </b-form-select>
              </div>
            </b-form-group>
            <b-form-group class="mb-1">
              <p class="cart-form-label">Время доставки:</p>
              <div class="cart-form-time mb-3">
                <b-form-select
                  v-model="selected" :options="options">
                  <b-form-select-option value="8">8:00 - 11:00</b-form-select-option>
                  <b-form-select-option value="12">12:00 - 15:00</b-form-select-option>
                  <b-form-select-option value="week">15:00 - 18:00</b-form-select-option>
                  <b-form-select-option value="week">19:00 - 22:00</b-form-select-option>
                </b-form-select>
              </div>
            </b-form-group>
          </div>
          <b-form-group class="cart-form-bottom px-4">
            <b-button type="submit" variant="primary" size="lg">Оформить заказ</b-button>
          </b-form-group>
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
      pagename: "Профиль"
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
.cart {
  &-title {
    font-size: 45px;
  }
  &-form {
    padding-top: 1.7rem;
    padding-bottom: .75rem;
    background-color: #F5F5F5;
    border-radius: 4px;
  }
  &-form-info {
    margin: 0;
    padding: 0;
  }
  &-form-label {
    margin-bottom: 0.5rem;
  }
  &-form-date{
    max-width: 195px;
  }
  &-form-time {
    max-width: 130px;
  }
  &-form-bottom {
    padding-top: 1.3rem;
    border-top: 2px solid #fff;
  }
}
</style>