<template>
    <div class="container">
        <div class="row">
            <div class="col-10 mx-auto">
                <h2 class="text-primary text-center">Bagnoles</h2>
                <bagnole-row v-for="(data, index) in data_bagnole" :key="index"/>
            </div>
        </div>
    </div>
</template>

<script>
    import BDD from '../BDD'
    import {onMounted } from 'vue'
    import BagnoleRow from '../components/BagnoleRow.vue'

    export default {
        name: "Home",
        components:{
            BagnoleRow
        },
        setup(){
            class Bagnole{
                constructor(marque,reference,image,kilometrage,note) {
                    this.marque = marque
                    this.reference =reference
                    this.image = image
                    this.note = note
                    this.kilometrage = kilometrage
                }
            }

            let data_bagnole = []

            const make_data_bagnole = () => {
                let three_bagnole = [];

                for (const bagnole of BDD) {
                    const new_bagnole = new Bagnole(bagnole.marque, bagnole.reference, bagnole.image, bagnole.kilometrage,bagnole.note)
                    //three_bagnole.push(new_bagnole)
                    if (three_bagnole.length === 2) {
                        three_bagnole.push(new_bagnole);
                        data_bagnole.push(three_bagnole)
                        three_bagnole = []
                    }else {
                        three_bagnole.push(new_bagnole);
                    }
                }
                console.log('ca marche?')
                console.log(data_bagnole)
            }

            onMounted(make_data_bagnole);

            return {
                data_bagnole
            }

        }
    }
</script>

<style scoped>

</style>