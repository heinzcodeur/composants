<template>
    <div class="row">
        <bagnole-card></bagnole-card>
        <bagnole-card></bagnole-card>
        <bagnole-card></bagnole-card>
       <!-- <h3 class="text-bg-danger">bagnole</h3> -->
    </div>
</template>

<script>
    import BagnoleCard  from './BagnoleCard.vue'

    export default {
        name: "BagnoleRow",
        components:{
            BagnoleCard
        }
    }
</script>

<style scoped>

</style>