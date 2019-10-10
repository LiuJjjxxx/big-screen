<template>
	<div class="box" style="height: 500px;width: 100%; margin-top: 10px;padding-bottom: 10px;">
		<div class="header">监控数据分析</div>
		<v-top></v-top>
		<v-bottom></v-bottom>
		
	</div>
</template>
<script>
	import analysistop from 'components/bottom_left/analysis-top'
	import analysisbottom from 'components/bottom_left/analysis-bottom'

	export default {
				 components: {
		    'v-top': analysistop,
		    'v-bottom': analysisbottom,
		    
  	},
	
	}
</script>

<style>
</style>