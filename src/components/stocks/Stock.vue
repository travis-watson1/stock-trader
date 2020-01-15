<template>
    <div class="col-sm-6 col-md-4">
        <div class="card" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title"> {{ stock.name }} <small>Price: {{ stock.price }}</small></h5>
                <input type="number" class="form-control" placeholder="Quantity" v-model.number="quantity" :class="{danger: insufficientFunds}">
                <br>
                <button href="#" :class="buttonClass" @click="buyStock" :disabled="insufficientFunds || quantity <= 0 || !Number.isInteger(quantity)">{{ insufficientFunds ? 'Insufficient Funds' : 'Buy'}}</button>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: ['stock'],
    data() {
        return {
            quantity: 0
        }
    },
    computed: {
        funds() {
            return this.$store.getters.funds;
        },
        insufficientFunds() {
            return this.quantity * this.stock.price > this.funds;
        },
        buttonClass() {
            return ( this.insufficientFunds ? 'btn btn-outline-danger' : 'btn btn-success') ;
        }
    },
    methods: {
        buyStock() {
            const order = {
                stockId: this.stock.id,
                stockPrice: this.stock.price,
                quantity: this.quantity
            };
            console.log(order);
            this.$store.dispatch('buyStock', order);
            this.quantity = 0;
        }
    }
}
</script>

<style scoped>
    .danger{
        border: 1px solid red !important;
    }
</style>