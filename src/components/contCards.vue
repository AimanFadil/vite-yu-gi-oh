<script>
import { store } from '../store.js';
import axios from 'axios';
import cards from '../components/cards.vue';

export default {
    name: 'contCards',
    components: {
        cards,

    },
    data() {
        return {
            store,

        }
    },
    methods: {
        getCardsList() {

            let archeUrl = store.endpoint

            if (store.archetype !== '') {
                archeUrl += `&archetype=${store.archetype}`;

            }
            console.log(archeUrl)

            axios.get(archeUrl).then((response) => {
                this.store.cardsList = response.data.data
            })
        },




    },
    created() {
        this.getCardsList();

    },
    computed: {
        arrayNumero() {
            return store.cardsList.length;
        }
    }
}
</script>
<template lang="">
  <div>
    <div class="but">
        <div v-if="arrayNumero > 0"><h2>Found {{ arrayNumero}}</h2></div>
        <div class="btn btn-success " @click="getCardsList">Cerca</div> 
    </div>
    <div class="container bg-white ">
        <div class="row">
            <div class="col-12" >
                <div class="content">
                    <cards v-for="card, index in store.cardsList" :key="index" :card="card"/>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../styles/generals.scss';

.but {
    padding: 15px;
    display: flex;
    justify-content: space-evenly;
    color: white;
    background-color: black;
}

.content {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    margin: 10px;
    background-color: white;




}
</style>