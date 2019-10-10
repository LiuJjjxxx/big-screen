<template>
		<div>
				<div id="anaiysis-bottom" style="width: 800px;height:250px;"></div>
		</div>
</template>

<script>
import echarts from 'echarts'
export default {
	methods:{	
	line(){
		var analysis_bottom_charts = echarts.init(document.getElementById('anaiysis-bottom'),'blue-science');
		
		var option = {
        	backgroundColor:'', //设置无背景色
			
    legend: {},
    tooltip: {},
    grid: {
	    		top:'10%',
	        left: '10%',
	        right: '0%',
	        bottom:'0%',
	        containLabel: true
	    },
    dataset: {
        source: [
            ['product', '2015', '2016', '2017'],
            ['Matcha Latte', 43.3, 85.8, 93.7],
            ['Milk Tea', 83.1, 73.4, 55.1],
            ['Cheese Cocoa', 86.4, 65.2, 82.5],
            ['Walnut Brownie', 72.4, 53.9, 39.1],
            ['Jiaxiang Brownie', 72.4, 53.9, 39.1]
            
        ]
    },
    xAxis: {type: 'category'},
    yAxis: {},
    // Declare several bar series, each will be mapped
    // to a column of dataset.source by default.
    series: [
        {type: 'bar'},
        {type: 'bar'},
        {type: 'bar'}
    ]
};

        analysis_bottom_charts.setOption(option);
	
		}
	},
	
	mounted(){
		 this.line()
		 
	}	
}


</script>

<style>
	#anaiysis-bottom{
		flex: 5;
		width: 1000px;
		height:400px;
		padding-left: 20px;
		padding-top: 10px;
	}
</style>