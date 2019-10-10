<template>
	<div class="alarm-flex box">
		<div class="alarm-left">
			<div class="header" style="text-align: left;">告警统计</div>
			<v-left></v-left>
		</div>
		<div class="alarm-right">
			<div class="header">告警统计</div>
			<v-right></v-right>
		</div>
		
	</div>
</template>

<script>
	import alarm_left from 'components/alarm/alarm-left'
	import alarm_right from 'components/alarm/alarm-right'

	export default {
				 components: {
		    'v-left': alarm_left,
		    'v-right':alarm_right,

  	},
	
	}
</script>

<style>
.alarm-flex{
	width: 100%;
	height: 412px;
	display: flex;
}
.alarm-left{
	flex: 5;
}
.alarm-right{
	flex: 5;
}

</style>