<template>
    <div class="cart-item-card">
        <div class="header">
            <h3>{{product.name}}</h3>
            <h4>In Cart: {{product.quantity}}</h4>
            <h4>Total Cost: {{item_cost.toFixed(2)}}</h4>
        </div>

        <p>{{description}}</p>

    </div>
</template>

<script>
export default {
    name:'CartItemCard',

    props:['product'],

    computed:{
        item_cost(){
            return this.product.price * this.product.quantity
        },

        description(){
            return this.product.description.substring(0,120);
        }
    }
}
</script>