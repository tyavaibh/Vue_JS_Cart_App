<template>
    <h1>Your Cart</h1>
    
    <CartItemCard 
    v-for="product in items"
    :key="product.id"
    :product="product"/>

    <CartSummaryPaymentCard/>

</template>


<script>
import CartItemCard from "../components/cart/CartItemCard"
import CartSummaryPaymentCard from "../components/cart/CartSummaryPaymentCard"

export default {
    name:'Cart',

    components:{
        CartItemCard,
        CartSummaryPaymentCard
    },

    computed:{
        items(){
            return this.$store.getters.cartItems
        }
    }
}
</script>

<style lang="scss">

    .cart-item-card{
        width: 90%;
        margin: 5%;
        background-color:white;
        box-shadow: 0 0 5px gray;
        border-radius: 5px;
        padding:10px;
        text-align: left;
        
        .header{
            display: flex;
            justify-content: space-around;

        }
    }

</style>