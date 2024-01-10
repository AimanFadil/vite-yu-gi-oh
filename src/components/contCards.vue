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
                    <div class="cards text-center" v-for="card, index in store.cardsList" :key="index">
                        <img :src="card.card_images[0].image_url" >
                        <div class="testo">
                            <p class="text-white">{{ card.name }}</p>
                            <p>{{ card.archetype }}</p>
                        </div>
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
    justify-content: center;
    flex-wrap: wrap;
    margin: 10px;


    .cards {
        width: calc(100% / 6 - 10px);
        padding: 10px;
        margin: 10px;

        .testo {
            background-color: rgba(212, 143, 56, 255);
            height: 90px;
        }

        img {
            width: 100%;
        }

    }
}
</style>