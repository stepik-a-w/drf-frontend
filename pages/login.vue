<template>
  <div class="py-5 my-5">
    <b-row align-h="center">
      <b-col cols="10">
        <b-card no-body class="login">
          <b-row align-h="center">
            <b-col>
              <b-img src="../assets/images/login.jpg" fluid alt=""></b-img>
            </b-col>
            <b-col class="pl-0">
              <b-form @submit="onSubmit" @reset="onReset" class="login-form">
                <div class="login-form-top">
                  <p class="h1 login-form-title">Войти</p>
                  <p class="login-form-text">Войдите, чтобы управлять <br>
                    или <a href="/signup" class="login-form-link">зарегистрируйтесь</a></p>
                  <b-alert variant="warning" show>Пароль неверный. Попробуйте снова</b-alert>
                </div>
                <div class="login-form-bottom">
                  <b-form-group
                    id="fieldset-1"
                    label="Электропочта:"
                    label-for="input-1"
                    :invalid-feedback="invalidFeedback"
                    :state="state"
                  >
                    <b-form-input id="input-1" v-model="email" :state="state" trim></b-form-input>
                  </b-form-group>
                  <b-form-group
                    id="fieldset-2"
                    label="Пароль"
                    label-for="input-2"
                    :invalid-feedback="invalidFeedback"
                    :state="state"
                  >
                    <b-form-input id="input-2" v-model="pass" :state="state" trim></b-form-input>
                  </b-form-group>
                  <b-form-group class="pt-2">
                    <b-button type="submit" variant="primary" size="lg">Зарегистрироваться</b-button>
                  </b-form-group>
                </div>
              </b-form>
            </b-col>
          </b-row>
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {

  layout: 'logining',

  data() {
    return {
      pagename: "Регистрация"
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
.login-form {
  padding: 2rem 1.5rem;
}
.login-form-bottom {
  padding-top: 1rem;
}
</style>