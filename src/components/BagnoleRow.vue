<template>
    <div class="row">
        <bagnole-card v-for="(card, i) in three_cars" :key="i" :car="card"/>


       <!-- <h3 class="text-bg-danger">bagnole</h3> -->
    </div>
</template>

<script>
    import BagnoleCard  from './BagnoleCard.vue'

    export default {
        name: "BagnoleRow",
        components:{
            BagnoleCard
        },
        props:{
            three_cars:Array
        }
    }
</script>

<style scoped>

</style>