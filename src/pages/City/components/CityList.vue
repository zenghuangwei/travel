<template>
    <div class="list" ref="wrapper"> 
        <div>
            <div class="area">
                <div class="title border-topbottom" >当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">{{this.currentCity}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom" >热门城市</div>
                <div class="button-list">
                    <div 
                        class="button-wrapper" 
                        v-for="item of hot" 
                        :key="item.id"
                        @click="handleCityClick(item.name)"
                    >
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div> 
            <div 
                class="area" 
                v-for="(item,key) of cities" 
                :key='key'
                :ref="key"
            >
                <div class="title border-topbottom" >{{key}}</div>
                <div class="item-list">
                    <div 
                        class="item border-bottom"
                        v-for="innerItem of item"
                        :key="innerItem.id"
                        @click="handleCityClick(innerItem.name)"
                    >
                        {{innerItem.name}}
                    </div>
                </div>
            </div>
            
        </div>
    </div>
</template>

<script>
    import Bscroll from 'better-scroll'
    import {mapState,mapMutations} from 'vuex'
    export default {
        name:'CityList',
        props:{
            cities:Object,
            hot:Array,
            letter:String
        },
        mounted(){
            this.scroll=new Bscroll(this.$refs.wrapper)
        },
        computed:{
            ...mapState({
                currentCity:'city'
            })
        },
        methods:{
            handleCityClick(city){
                this.changeCity(city)
                this.$router.push('/')
            },
            ...mapMutations(['changeCity'])
        },
        watch:{
            letter(){
                if(this.letter){
                    const element =this.$refs[this.letter][0]//注意ref加：与不加：的区别https://www.jianshu.com/p/3bd8a2b07d57
                    
                    this.scroll.scrollToElement(element)//better-scroll 提供的接口
                }
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .border-topbottom
        &:before
            border-color:#ccc
        &:after
            border-color:#ccc
    .border-bottom
        &:before
            border-color:#ccc
    .list 
        overflow:hidden
        position:absolute
        top:1.58rem 
        left:0
        right:0
        bottom:0
        .title
            line-height:.54rem 
            background:#eee
            padding-left:.2rem 
            font-size:.26rem 
            color:#666 
        .button-list
            overflow:hidden
            padding:.1rem .6rem .1rem .1rem 
            .button-wrapper
                float:left
                width:33.33%
                .button
                    margin:.1rem 
                    padding:.1rem 0
                    border-radius:.1rem
                    text-align:center 
                    border:.02rem solid #ccc 
        .item-list
            .item
                line-height:.76rem 
                padding-left:.2rem 
</style>