<style lang="stylus" rel="stylesheet/stylus">
.mainApp
  position absolute
  height 100%
  width 100%
.box
	padding:0px
	width: 400px
	height: 200px
	background: #0e1533
	border: 1px solid #0e2649
.header
	padding-top :15px
	padding-left: 10px
	text-align: left
	color: #049ae3
body 
	overflow: hidden
.header:before
		content: "　　"
		height: 20px
		width: 20px
		padding-top:8px
		margin-right:8px
		background: url(../src/assets/img/header.png) no-repeat
		background-size: 100%
</style>

<template>
<div class="mainApp">
  <router-view class="router-view"></router-view>
</div>

</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      seller: {}
    }
  },
  created() {}
}

</script>
