<template>
    <div>
        <div class="title"><img class="title-img" src="https://imgs.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png"><span class='title-desc'>猜你喜欢</span></div>
        <ul>
            <li class='item' v-for='item of recommendList' :key="item.id">
                <img class="item-img" :src="item.imgUrl" alt="">
                <div class="item-info">
                    <div class="item-title">{{item.title}}</div>
                    <div class="item-desc">{{item.desc}}</div>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>

    </div>
</template>

<script>
    export default {
        name:'HomeRecommend',
        data(){
            return {
                recommendList:[{
                    id:'0001',
                    imgUrl:'https://imgs.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
                    title:'临安湍口众安氡温泉',
                    desc:'临安湍口众安氡温泉+水上恒温水世界成人票（赠养生餐1份）'
                },{
                    id:'0002',
                    imgUrl:'https://imgs.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
                    title:'临安湍口众安氡温泉',
                    desc:'临安湍口众安氡温泉+水上恒温水世界成人票（赠养生餐1份）'
                },{
                    id:'0003',
                    imgUrl:'https://imgs.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
                    title:'临安湍口众安氡温泉',
                    desc:'临安湍口众安氡温泉+水上恒温水世界成人票（赠养生餐1份）'
                }]
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '~styles/mixins.styl'
    .title
        position:relative
        padding:.28rem 0 0
        .title-img
            display:inline-block
            overflow:hidden
            width:.3rem 
            height:.3rem 
            margin-left:.2rem 
            vertical-align :top
        .title-desc
            display:inline-block
            margin-left :.08rem
            height:.44rem 
            color:#212121
            font-size: .32rem
            line-height :.44rem
    .item
        display:flex
        overflow:hidden
        height:2rem 
        padding:.2rem 0
        .item-img 
            width:2rem 
            height:2rem 
        .item-info
            flex:1
            padding:.1rem 
            min-width :0
            .item-title
                line-height :.54rem
                font-size:.32rem 
                color:#212121
                ellipsis()
            .item-desc
                line-height :.4rem
                margin-top:.14rem
                color:#616161
                ellipsis()
            .item-button
                line-height :.44rem
                margin-top:.2rem
                background:#ff9300 
                padding: 0 .2rem
                border-radius: .06rem
                color:#fff
</style>