<script>
export default {
    name: 'cards',
    props: {
        card: Object,
    },
    data() {
        return {

        }
    }
}
</script>
<template lang="">
    <div class="cards text-center">
        <img :src="card.card_images[0].image_url" >
        <div class="testo">
            <p class="text-white">{{ card.name }}</p>
            <p>{{ card.archetype }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/generals.scss';

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
</style>