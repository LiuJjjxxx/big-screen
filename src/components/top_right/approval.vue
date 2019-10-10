<template>
  <div class="box">
	<div class="header">申请</div>
		<div class="approval-flex">
			<div class="approval-left">

				<div>已审批 : 15份</div>
				<div>待审批 : 10份</div>
				<div></div>
			</div>
			<div class="approval-right"> 
				<div>龙岗妇幼</div>
				<div>神州动力</div>
				<div>美易佳</div>
				<div>王老吉</div>
			</div>
		</div>
		
		
	</div>
	
  </div>
</template>

<script>
</script>

<style>
	.approval-flex{
		display: flex;
		color: white;
	}
	.approval-left{
		border-image: linear-gradient(blue,red) 30 30; 
		border-right: 2px solid;
		margin-top: 30px;
		flex: 4;
	}
	.approval-right{
		flex: 6;
	}
	.approval-left>div{
		text-align: center;
		padding-top : 15px;
	}
	.approval-right>div{
		padding-left: 10px;
		padding-top : 15px;
	}
</style>