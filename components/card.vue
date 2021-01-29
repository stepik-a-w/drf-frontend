<template>


    <b-card class="col-4"
            :title= "title"
            :img-src= "img"
            img-alt=""
            img-top
            img-width="300">

        <b-row class="pt-3" align-v="center">
            <b-col>
                <b-form-spinbutton v-if="qty>0" v-on:click="addToCart" id="item-counter" v-model="qty"  min="0" max="100" step="1"></b-form-spinbutton>
                <b-button v-if="qty==0" v-on:click="qty+=1, addToCart" variant="primary">В корзинку</b-button>
            </b-col>
            <b-col class="items-cards-price">
                {{ price }} P
            </b-col>
        </b-row>
    </b-card>


</template>

<script>

    export default {

        layout: 'default',

        props: {

            'id' : {
                type: Number,
                default: 0,
            },

            'title': {
               // type: String,
                default: "",
            },

            'description': {
                type: String,
                default: "",
            },

            'price':{
               // type: Number,
                default: 0,
            },
            'img':{
               // type: String,
                default: "",
            },

        },

        data() {
            return {
                host: "http://127.0.0.1:8000/api/v1",
                qty: 0
            }
        },

        methods: {

            addToCart: function() {

                console.log("Вызвано добавление в корзину")

                var data = {
                    "item": {
                        "title": this.title,
                        "description": this.description,
                        "weight": 0,
                        "price": this.price,
                    },
                    "item_id": this.id,
                    "quantity": this.qty,
                }

                this.$axios.$post(this.host+'/carts/items',data).then((result) => {

                    console.log("Добавлено в корзину")

                }).catch((error) => {

                    console.log("Не удалось добавить")
                    console.log(error)
                })

            }
        },

        watch: {
            qty: function (val) {

                this.addToCart()

            },
        },

    }


</script>


