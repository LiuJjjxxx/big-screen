<!-- 饼图 -->

<template lang="html">
	<div >
		<div id="right"style="width: 400px;height:180px;"></div>
		<div id="right1"style="width: 400px;height:180px;"></div>
	</div>
</template>

<script>
import echarts from 'echarts'
import echartsGL from 'echarts-gl'
export default {
	mounted(){
		var myChart = echarts.init(document.getElementById('right'),'purple-passion');
		var myChart1 = echarts.init(document.getElementById('right1'),'purple-passion');
        // 指定图表的配置项和数据
        var option = {
		backgroundColor:'', //设置无背景色
	    tooltip : {
	        trigger: 'axis',
	        axisPointer : {            // 坐标轴指示器，坐标轴触发有效
	            type : 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
	        }
	    },
	    grid: {
	    		top:'10%',
	        left: '3%',
	        right: '4%',

	        containLabel: true
	    },
	 
	    xAxis : [
	        {
	            type : 'category',
	            data : ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'],
	            axisTick: {
	                alignWithLabel: true
	            }
	        }
	    ],
	    yAxis : [
	        {
	            type : 'value'
	        }
	    ],
	    series : [
	        {	
	        		itemStyle:{
	        			normal:{
	        				color: function(params) {
                            // build a color map as your need.
                            var colorList = [
                              '#9b8bba','#e098c7','#8fd3e8','#71669e','#cc70af','#7cb4cc'
                            ];

                            return colorList[params.dataIndex]

                        },
	        			}
	        		},
	            name:'直接访问',
	            type:'bar',
	            barWidth: '60%',
	            data:[10, 52, 200, 334, 390, 330]
	        }
	    ]
	};

        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);
         myChart1.setOption(option);
		 
	}	
}


</script>

<style lang="stylus">
	.my-color{
		color: red;
	}
</style>
