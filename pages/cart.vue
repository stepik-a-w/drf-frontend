<template>
  <div>

    <h1 class="h1 mb-4 cart-title">Корзина</h1>

    <b-row class="pb-5">

      <b-col cols="8">
        <b-row class="items-cards">

          <b-card-group v-for="cart_item in cart_items" deck class="items-cards">

            <b-col cols="" v-if="cart_item.quantity>0">

              <card
                      :id="cart_item.item.id"
                      :img="cart_item.item.image"
                      :title="cart_item.item.title"
                      :price="cart_item.price"
                      :qty="cart_item.quantity"
              />

            </b-col>
          </b-card-group>

        </b-row>

      </b-col>

    </b-row>
  </div>
</template>
<script>


    export default {

        layout: 'default',

        data() {
            return {
                cart_items: [],
                host: "http://127.0.0.1:8000/api/v1",
            }
        },

        methods: {

            loadData: function() {
                this.$axios.$get(this.host+'/carts/items').then((result) => {

                    this.cart_items = result.results
                    console.log(this.cart_items);
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