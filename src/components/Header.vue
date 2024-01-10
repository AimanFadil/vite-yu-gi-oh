<script>
export default {
    name: 'Header',
    data() {
        return {

        }
    }
}
</script>
<template lang="">
  <div>
    <header>
       <img src="https://occ-0-2794-2219.1.nflxso.net/dnm/api/v6/LmEnxtiAuzezXBjYXPuDgfZ4zZQ/AAAABdpYalFU9SD9K6dNwu9SlKsNaQ3AIGWFrN_uDy6R7N3TS5DHIatIETtgeqwC0kM01zJyor2znGql_ixTWzVueA-GllV7Hn03ygETN_Nd7oZA.png?r=81f" alt="">
       <h1>Yu-Gi-Oh Api</h1>
    </header>
  </div>
</template>

<style lang="scss" scoped>
@use '../styles/generals.scss';

header {
    height: 100px;
    padding: 10px;
    display: flex;

    img {
        width: 10%;
    }

    h1 {

        line-height: 90px;
    }
}
</style>