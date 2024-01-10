<script>
import { store } from '../store.js';
import axios from 'axios';
export default {
    name: 'contCards',
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
                    <div class="cards text-center" v-for="card, index in store.cardsList[0].card_images" :key="index">
                        <img :src="card.image_url" >
                    </div>
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
    flex-direction: row;
    flex-wrap: wrap;

    .cards {
        width: calc(100% / 5 - 10px);
        padding: 20px;
    }
}
</style>