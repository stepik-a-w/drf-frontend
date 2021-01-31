<template>
  <div>
    <b-navbar class="page-footer" toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="/" class="page-footer-logo">
        <b-img src="../assets/images/logo.png" alt="Stepik Packages" width="190"></b-img>
      </b-navbar-brand>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item :to="'/settings'" href="#" class="px-3">Настройки</b-nav-item>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>

</script>

<style lang="scss">
  .page-footer {
    padding-top: .8rem;
    padding-bottom: .8rem;
    margin-top: 30px;
    margin-bottom: 20px;
    border-radius: 4px;

    &.bg-dark {
      background-color: #222516 !important;

      .nav-link {
        font-size: 18px;
        color: #fff;
        text-decoration: underline;
      }
    }

    
  }
</style>