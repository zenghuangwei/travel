<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img
          class="swiper-img"
          :src="item.imgUrl"
        />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  data: function() {
    return {
      swiperOption: {
				pagination:'.swiper-pagination',
				loop:true
			},
			swiperList:[{
				id:'0001',
				imgUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201910/e7eac5a5e99e6517c61b953c0fece63b.jpg_750x200_4b701cf8.jpg'
			},{
				id:'0002',
				imgUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201911/1a3988d46c7db7d3848fa50460e5eb07.jpg_750x200_6382fd3e.jpg'
			}]
    };
  }
};
</script>

<style lang="stylus" scoped>
	.wrapper>>>.swiper-pagination-bullet-active
		background:#fff
	.wrapper
		overflow:hidden
		width:100%
		height:0
		padding-bottom:31.25%
		.swiper-img 
			width: 100%;
</style>