<template>
	<div class="box" style="height: 500px;width: 98%; margin-top: 10px;padding-bottom: 10px;">
		<div class="header">监控数据分析</div>
		<v-top-two></v-top-two>
		<v-bottom-two></v-bottom-two>
		
	</div>
</template>
<script>
	import analysistoptwo from 'components/bottom_right/analysis-top'
	import analysisbottomtwo from 'components/bottom_right/analysis-bottom'

	export default {
				 components: {
		    'v-top-two': analysistoptwo,
		    'v-bottom-two': analysisbottomtwo,
		    
  	},
	
	}
</script>

<style>
</style>