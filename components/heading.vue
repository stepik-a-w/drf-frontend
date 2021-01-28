<template>
  <div>
    <b-navbar class="page-header" toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="/" class="page-header-logo"><b>Stepik Packages</b></b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
        <b-nav-item href="#" >Корзина (0)</b-nav-item>
        <b-nav-item href="#" class="ml-4">Глеб Кушедов</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>

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