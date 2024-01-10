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
        <contCards/>
    </main>
</template>


<style lang="scss" scoped>
@use '../styles/generals.scss';

main {
    background-color: rgba(212, 143, 56, 255);
    height: 100vh;


}
</style>