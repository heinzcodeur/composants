<template>
    <div class="card" style="width: 18rem;">
        <img class="card-img-top" :src="changeBackground" alt="Card image cap">
        <div class="card-body">
            <p class="card-text">{{ car.marque }} {{ car.reference}}</p>
        </div>
    </div>
</template>


<script>
     import { computed } from 'vue'

    export default {
        name: "BagnoleCard",
        props:{
            car:Object
        },
         setup(props){
             const changeBackground = computed(() => {
                    return  `${props.car.image}`;
             })

             return {
                 changeBackground
             }
         }
    }
</script>

<style scoped>

</style>