<script>
import contCards from '../components/contCards.vue'
import { store } from '../store.js';
export default {
    components: {
        contCards,
    },
    name: 'Main',
    data() {
        return {
            store,
            allArchetype: [
                'Archfiend',
                'Magistus',
                'Noble Knight',
                'Paleozoic'
            ]
        }
    }

}
</script>
<template lang="">
    <main>
        <div class="diff">
            <select class="form-select" aria-label="Default select example" v-model="this.store.archetype">
                <option id="filter" >Select Archetype</option>
                <option v-for="archetype, index in allArchetype" :key="index" :value="archetype">{{ archetype }}</option>
            </select>
        </div>
        <contCards/>
    </main>

</template>


<style lang="scss" scoped>
@use '../styles/generals.scss';

main {

    height: 100%;

    .diff {

        width: 200px;
        padding: 20px;
        height: 150px;
    }
}
</style>