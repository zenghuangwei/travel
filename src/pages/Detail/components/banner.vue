<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img
                class="banner-img"
                src="http://img1.qunarzz.com/sight/p0/1411/b6/662fc49d1d26a5a7775cf6b7f8b4ecec.water.jpg_600x330_c34588e7.jpg" 
            >
            <div class="banner-info">
                <div class="banner-title">杭州野生动物世界(AAAA景区)</div>
                <div class="banner-number">
                    <span class="iconfont banner-icon">&#xe649;</span>
                    46
                </div>
            </div>
        </div>
        <common-gallary 
            :imgs='imgs' 
            v-show="showGallary"
            @close="handleGallaryClose"
        ></common-gallary>
    </div>
</template>

<script>
    import CommonGallary from 'common/gallary/Gallary'
    export default {
        name:'DetailBanner',
        components:{
            CommonGallary
        },
        data (){
            return {
                imgs:[
                    'http://img1.qunarzz.com/sight/p0/1411/b6/662fc49d1d26a5a7775cf6b7f8b4ecec.water.jpg_350x240_b184c0cd.jpg',
                    'http://img1.qunarzz.com/sight/p0/1902/d9/d93010284bcaaefda3.img.jpg_350x240_8a5bea15.jpg'
                ],
                showGallary:false
            }
        },
        methods:{
            handleBannerClick(){
                this.showGallary=true
            },
            handleGallaryClose(){
                this.showGallary=false
            }
        }
    } 
</script>

<style lang="stylus" scoped>
    .banner
        position:relative
        overflow :hidden
        height:0
        padding-bottom:55%
        .banner-img
            width:100%
        .banner-info
            display :flex 
            position:absolute
            left:0
            right:0
            bottom:0
            line-height:.6rem 
            background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
            color:#fff
            .banner-title
                flex:1
                font-size:.32rem 
                padding: 0 .2rem 
            .banner-number
                margin-top:.14rem
                padding:0 .4rem
                height:.32rem 
                line-height :.32rem
                border-radius:.2rem 
                font-size:.24rem
                background:rgba(0,0,0,0.8)
                .banner-icon
                    font-size:.24rem
        
</style>