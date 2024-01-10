<script>
import contCards from '../components/contCards.vue'
export default {
    components: {
        contCards,
    },
    name: 'Main',
    data() {
        return {

        }
    }
}
</script>
<template lang="">
    <main>
        <div class="diff">
            <select class="form-select" aria-label="Default select example">
                <option selected>Alien</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
        </div>
        <contCards/>
    </main>
</template>


<style lang="scss" scoped>
@use '../styles/generals.scss';

main {
    background-color: rgba(212, 143, 56, 255);
    height: 100%;

    .diff {
        background-color: rgba(212, 143, 56, 255);
        width: 200px;
        padding: 20px;
        height: 150px;
    }
}
</style>