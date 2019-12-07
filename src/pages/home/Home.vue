<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icon></home-icon>
    </div>
</template>

<script>

import HomeHeader from './components/header'
import HomeSwiper from './components/Swiper'
import HomeIcon from './components/HomeIcons'

export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcon
    } 

}
</script>

<style lang="stylus">

</style>