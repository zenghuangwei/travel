<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
	<router-link to="/city">
		<div class="header-right">
			{{this.city}}
			<span class="iconfont arrow-icon">&#xe744;</span>
		</div>
	</router-link>
  </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
  name: "HomeHeader",
  computed:{
	  ...mapState(['city'])//将store里的数据映射成组件的计算属性中
  }
};
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
.header
	display:flex
	line-height:$headerHeight
	background:$bgColor
	color:#fff
	.header-left
		width:.64rem
		float:left
		.back-icon
			text-align:center
			font-size:.36rem 
	.header-input
		flex:1
		height:.64rem
		line-height:.64rem
		margin-top:.12rem
		margin-left:.2rem
		background:#fff
		border-radius:.1rem
		color:#ccc
	.header-right
		min-width:1.04rem
		padding:0 .1rem
		float:right
		text-align:center
		color:#fff
		.arrow-icon
			margin-left:-.04rem 
			font-size:.28rem
</style>
