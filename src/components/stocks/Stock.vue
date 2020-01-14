<template>
    <div class="col-sm-6 col-md-4">
        <div class="card" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title"> {{ stock.name }} <small>Price: {{ stock.price }}</small></h5>
                <input type="number" class="form-control" placeholder="Quantity" v-model.number="quantity">
                <br>
                <button href="#" class="btn btn-success" @click="buyStock" :disabled="quantity <= 0 || !Number.isInteger(quantity)">Buy</button>
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
    methods: {
        buyStock() {
            const order = {
                stockId: this.stock.id,
                stockPrice: this.stock.price,
                quantity: this.quantity
            };
            console.log(order);
            this.quantity = 0;
        }
    }
}
</script>