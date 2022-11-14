<template>
    <div class="container">
        <div class="row">
            <div class="col-10 mx-auto">
                <bagnole-row v-for="(data, i) in data_bagnole" :key="i" :three_cars="data"/>
            </div>
        </div>
    </div>
</template>
<script>
    import BDD from '../BDD'
    import BagnoleRow from '../components/BagnoleRow.vue'
    import { onMounted, ref } from 'vue'

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

            let data_bagnole = ref([])

            const make_data_bagnole = () => {
                let three_bagnole = [];

                for (const bagnole of BDD) {
                    const new_bagnole = new Bagnole(bagnole.marque, bagnole.reference, bagnole.image, bagnole.kilometrage,bagnole.note)
                    //three_bagnole.push(new_bagnole)
                    if (three_bagnole.length === 2) {
                        three_bagnole.push(new_bagnole);
                        data_bagnole.value.push(three_bagnole)
                        three_bagnole = []
                    }else {
                        three_bagnole.push(new_bagnole);
                    }
                }
                // console.log('ca marche?')
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