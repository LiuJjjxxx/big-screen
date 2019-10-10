<template>
	<div class="box">
		<div class="header">监控数量</div>
		<div class="count-msg">
			<ul>
				<li><span>服务器</span><a>30</a>台</li>
				<li><span>AC</span><a>12</a>台</li>
				<li><span>交换机</span><a>6</a>台</li>
				<li><span>在线人数</span><a>30</a>人</li>
				<li><span>路由器</span><a>53</a>台</li>
				<li><span>数据库</span><a>1</a>个</li>
			</ul>
		</div>
	</div>
</template>

<script>
</script>

<style>
	.count-msg>ul{
		margin: 0px;
		padding: 0px;
		
	}
	.count-msg>ul>li{
		margin: auto;
		display: block;
		width: 100px;
		color: #029de7;
		font-size: 5px;
		float: left;
	}
	.count-msg>ul>li>span{
		padding-left: 10px;
		font-size: 20px;
		color: white;
		display: block;
	}
	.count-msg>ul>li>a{
		padding-left: 10px;
		color: #029de7;
		margin: auto;
		font-size: 40px;
	}
</style>