<script>
import { store } from '../store.js';
import axios from 'axios';
import cards from '../components/cards.vue'
export default {
    name: 'contCards',
    components: {
        cards
    },
    data() {
        return {
            store,
        }
    },
    methods: {
        getCardsList() {
            axios.get(store.endpoint).then((response) => {
                this.store.cardsList = response.data.data
            })
        }

    },
    created() {
        this.getCardsList();

    },
}
</script>
<template lang="">
  <div>
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

.content {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    margin: 10px;



}
</style>