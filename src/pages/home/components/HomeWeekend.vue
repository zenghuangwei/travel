<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class='item' v-for='item of recommendList' :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl" alt="">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name:'HomeWeekend',
        data(){
            return {
                recommendList:[{
                    id:'0001',
                    imgUrl:'https://imgs.qunarzz.com/sight/source/1811/52/b6776b49d27025.jpg_r_640x214_35ae205c.jpg',
                    title:'美丽普陀山',
                    desc:'人间仙境杭州，佛教圣地普陀山等你来玩！在这里静心接收佛家的洗礼，用心感受佛文化'
                },{
                    id:'0002',
                    imgUrl:'https://imgs.qunarzz.com/sight/source/1811/52/b6776b49d27025.jpg_r_640x214_35ae205c.jpg',
                    title:'美丽普陀山',
                    desc:'人间仙境杭州，佛教圣地普陀山等你来玩！在这里静心接收佛家的洗礼，用心感受佛文化'
                },{
                    id:'0003',
                    imgUrl:'https://imgs.qunarzz.com/sight/source/1811/52/b6776b49d27025.jpg_r_640x214_35ae205c.jpg',
                    title:'美丽普陀山',
                    desc:'人间仙境杭州，佛教圣地普陀山等你来玩！在这里静心接收佛家的洗礼，用心感受佛文化'
                }]
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '~styles/mixins.styl'
    .title
        margin-top:.2rem 
        line-height:.8rem 
        background:#eee
        text-indent:.2rem 
    .item-img-wrapper
        overflow :hidden
        height:0
        padding-bottom:33.9%
        .item-img
            width:100%
    .item-info
        padding:.14rem .2rem .2rem .2rem 
        .item-title
            padding-right:1.4rem 
            line-height :.48rem
            font-size:.28rem 
            color:#212121
            ellipsis()
        .item-desc
            line-height :.42rem
            font-size:.24rem 
            padding-right:1.4rem 
            color:#616161
            ellipsis()

    
</style>