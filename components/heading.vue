<template>
  <div>
    <b-navbar class="page-header" toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand :to="'/'" class="page-header-logo"><b>Stepik Packages</b></b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">

            <b-nav-item v-if="$store.state.is_logged" href="#" :to="'/cart'" >Корзина (0)</b-nav-item>
            <b-nav-item v-if="$store.state.is_logged" :to="'/profile'" class="ml-4">Глеб Кушедов</b-nav-item>
            <b-nav-item v-if="$store.state.is_logged" v-on:click="logout" class="ml-4">Выйти</b-nav-item>

            <b-nav-item v-if="!$store.state.is_logged" :to="'/login'" class="ml-4">Войти</b-nav-item>
            <b-nav-item v-if="!$store.state.is_logged" :to="'/register'" class="ml-4">Регистрация</b-nav-item>

        </b-navbar-nav>

      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>

    export default {

        data() {
            return {
                tokenok: false,
            }
        },

        methods: {

            logout: function() {

                this.$store.dispatch('make_logout');

                this.$router.push('/login');

            }
        },

        created() {

            var token = this.$auth.$storage.getLocalStorage("token");

            if (token!=null){
                this.tokenok = true;
            }

        },

    }

</script>

<style lang="scss">
  .page-header {
    margin-top: 20px;
    margin-bottom: 35px;
    padding-top: 11px;
    padding-bottom: 11px;
    font-size: 18px;
    border-radius: 4px;

    &.bg-dark {
      background-color: #222516 !important;
    }

    &-logo {
      margin-right: 7rem;
      font-family: 'Helvetica Neue', sans-serif;
      font-size: 20px;
    }

    .navbar-nav .nav-link {
      color: #fff;
    }
  }
</style>