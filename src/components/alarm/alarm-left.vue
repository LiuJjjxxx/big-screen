<!-- 饼图 -->

<template lang="html">
	<div>
		<div  id="main" style="width: 600px;height:400px;"></div>

		
	</div>

</template>

<script>
import echarts from 'echarts'
export default {
	mounted(){
		var myChart = echarts.init(document.getElementById('main'),'blue-science');
        // 指定图表的配置项和数据
        var option = {
        	backgroundColor:'', //设置无背景色
    tooltip: {
        trigger: 'item',
        formatter: "{a} <br/>{b}: {c} ({d}%)"
    },
    legend: {

        x : 'center',
    		y : '80%',
        data:['未分类','信息','告警','平均','高','灾难']
    },
    series: [
        {
            name:'访问来源',	
            type:'pie',
            center: ['50%', '40%'],
            radius: ['50%', '60%'],
            avoidLabelOverlap: false,
            label: {
                normal: {
                    show: false,
                    position: 'center'
                },
                emphasis: {
                    show: true,
                    textStyle: {
                        fontSize: '30',
                        fontWeight: 'bold'
                    }
                }
            },
            labelLine: {
                normal: {
                    show: false
                }
            },
            data:[
                {value:335, name:'未分类'},
                {value:310, name:'信息'},
                {value:234, name:'告警'},
                {value:135, name:'平均'},
                {value:1548, name:'高'},
                {value:1548, name:'灾难'},
            ]
        }
    ]
};

        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);

		 
	}	
}


</script>

<style lang="stylus">
</style>
