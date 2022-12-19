<template>
    <div class="spinner" v-if="spinnerDisplay">
        <Spinner/>
    </div>
    <div class="products" v-else>
        <div class="card m-2 mx-auto" v-for="item in productsHardware" :key="item" style="width: 18rem;">
            <img :src="item.image" class="card-img-top" alt="...">
            <div class="card-body">
                <h6>{{ item.name }}</h6>
                <h6>R {{ item.price }}</h6>
            </div>
        </div>
    </div>
</template>

<script>
import Spinner from '@/components/spinnerComponent.vue'
export default {
    components: {
        Spinner
    },
    data() {
        return {
            productsHardware: [
                {
                    name: 'Corsair DRAM ',
                    price: 9999,
                    image: 'https://i.postimg.cc/K8R7QJ0d/RAM.jpg'
                },
                {
                    name: 'ASUS GeForce GPU',
                    price: 39999,
                    image: 'https://i.postimg.cc/vZkrKfjD/Graphics-Card.jpg'
                },
                {
                    name: 'AMD Ryzen CPU',
                    price: 14999,
                    image: 'https://i.postimg.cc/RCLT033b/CPU.jpg'
                },
                {
                    name: 'Intel Motherboard',
                    price: 8499,
                    image: 'https://i.postimg.cc/pdjfMybC/Mother-Board.jpg'
                }
            ],
           spinnerDisplay: true, 
        }
    },
mounted() {
    setTimeout(() => {
        this.spinnerDisplay = false
        console.log(this.spinnerDisplay);
    }, 2000)
}
}
</script>

<style scoped>
.products{
    display: flex;
}

.spinner{
    margin-top: 200px;
}

.card{
    border: 2px solid black;
    background-color: lightgreen;
}

</style>