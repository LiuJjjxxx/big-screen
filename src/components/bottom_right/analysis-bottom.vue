<template>
		<div>
				<div id="anaiysis-bottom-two" style="width: 1000px;height:250px;"></div>
		</div>
</template>

<script>
import echarts from 'echarts'
export default {
	methods:{	
	line(){
		var analysis_bottom_charts_two = echarts.init(document.getElementById('anaiysis-bottom-two'),'blue-science');
		
		var option = {
    xAxis: {
        type: 'category',
        data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
    },
    yAxis: {
        type: 'value'
    },
      legend: {
        orient: 'vertical',
      	
       data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
		x:'90%',
		y:'center'
    },
    series: [{
    		name:'Mon',
        data: [820, 932, 901, 934, 1290, 1330, 1320],
        type: 'line',
        markPoint:{
						symbol: "pin", //标注类型
						symbolSize: 20 , //标记大小
						
						data:[
							{type: "max", name: "最大值"},
						]
					},
        smooth: true,
        symbol:'none',
    },{
    		name:'Tue',
        data: [0, 80, 500, 666, 250, 444,140 ],
        markPoint:{
						symbol: "pin", //标注类型
						symbolSize: 20 , //标记大小
						
						data:[
							{type: "max", name: "最大值"},
						]
					},
        type: 'line',
        smooth: true,
        symbol:'none',
        
    },{
    		name:'Wed',
        data: [45, 752, 700, 600, 50, 400,666 ],
        markPoint:{
						symbol: "pin", //标注类型
						symbolSize: 20 , //标记大小
						
						data:[
							{type: "max", name: "最大值"},
						]
					},
        type: 'line',
        smooth: true,
        symbol:'none',
    },
    ]
};

        analysis_bottom_charts_two.setOption(option);
	
		}
	},
	
	mounted(){
		 this.line()
		 
	}	
}


</script>

<style>
	#anaiysis-bottom-two{
		flex: 5;
		width: 800px;
		height:400px;
		padding-left: 20px;
		padding-top: 10px;
	}
</style>