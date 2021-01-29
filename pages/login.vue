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
              <b-form  class="login-form">
                <div class="login-form-top">
                  <p class="h1 login-form-title">Войти</p>
                  <p class="login-form-text">Войдите, чтобы управлять <br>
                    или <a href="/signup" class="login-form-link">зарегистрируйтесь</a></p>

                  <b-alert variant="warning" v-if="isloginincorrect" show>Пароль неверный. Попробуйте снова</b-alert>

                </div>
                <div class="login-form-bottom">
                  <b-form-group
                    id="fieldset-1"
                    label="Электропочта:"
                    label-for="input-1"
                    :invalid-feedback="invalidFeedback"
                  >
                    <b-form-input id="input-1" v-model="userdata.username" trim></b-form-input>
                  </b-form-group>
                  <b-form-group
                    id="fieldset-2"
                    label="Пароль"
                    label-for="input-2"
                    :invalid-feedback="invalidFeedback"
                  >
                    <b-form-input id="input-2" v-model="userdata.password"  trim></b-form-input>
                  </b-form-group>
                  <b-form-group class="pt-2">
                    <b-button v-on:click="tryAuth" variant="primary" size="lg">Войти</b-button>
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


    import { BForm } from 'bootstrap-vue'

    export default {

        layout: 'default',

        data() {
            return {
                pagename: "Форма авторизации",
                isloginincorrect: false,
                host: "http://127.0.0.1:8000/api/v1",
                invalidFeedback: "Неверный логин или пароль",
                userdata: {username: "admin", password: "admin"}
            }
        },


        methods: {

            tryAuth () {

                 this.$axios.$post(this.host+'/users/auth/login', this.userdata).then((result) => {

                        let token = result.token;

                        this.$auth.$storage.setLocalStorage("token", token);
                        this.$axios.setToken('Token'+" "+token);

                        this.isloginincorrect = false;

                        console.log("Токен записан")

                        return redirect({name:'item'});

                 }).catch((error) => {

                     console.log("Произошла ошибка, смотрите в консоль");

                     this.isloginincorrect = true;



                })

            },



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