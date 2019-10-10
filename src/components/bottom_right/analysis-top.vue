<template>
		<div style="display: flex;;">
				<div id="anaiysis-top-left-two"></div>
				<div id="anaiysis-top-right-two" style="width: 300px;height: 200px; flex: 5;"></div>
		</div>
</template>

<script>
import echarts from 'echarts'
export default {
	methods:{
		pie(){

			var myChart = echarts.init(document.getElementById('anaiysis-top-left-two'),'blue-science');
        // 指定图表的配置项和数据
        var option = {
    tooltip: {
        trigger: 'item',
        formatter: "{a} <br/>{b}: {c} ({d}%)"
    },
    legend: {
        orient: 'vertical',
        x: '250',
        y:'center',
        data:['直接访问','邮件营销','联盟广告','视频广告','搜索引擎']
    },
    series: [
        {
            name:'访问来源',
            type:'pie',
            radius: ['50%', '70%'],
            center:['20%','center'],
            avoidLabelOverlap: false,
            label: {
                normal: {
                    show: false,
                    position: 'center'
                },
                emphasis: {
                    show: true,
                    textStyle: {
                        fontSize: '20',
                        fontWeight: 'bold'
                    }
                }
            },
            itemStyle: {
                //通常情况下：
                normal: {
                    //每个柱子的颜色即为colorList数组里的每一项，如果柱子数目多于colorList的长度，则柱子颜色循环使用该数组
                    color: function (params) {
                        var colorList = ['#0786f0', '#0367e7', '#bfcc23', '#c69739', '#cd6037']; //每根柱子的颜色
                        return colorList[params.dataIndex];
                    }
                }
              },
            labelLine: {
                normal: {
                    show: false
                }
            },
            data:[
                {value:335, name:'直接访问'},
                {value:310, name:'邮件营销'},
                {value:234, name:'联盟广告'},
                {value:135, name:'视频广告'},
                {value:1548, name:'搜索引擎'}
            ]
        }
    ]
};

	var rotation = 0;
        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);

		},
	line(){
		var myChart11 = echarts.init(document.getElementById('anaiysis-top-right-two'),'blue-science');

		var option = {
		backgroundColor:'',
			
    xAxis: {
        type: 'category',

        boundaryGap: false,
        data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],	
        axisLine:{
                		lineStyle: {
                       color: '#fff'
                  }       		
           },
    },
    yAxis: {
        type: 'value',
        name:'XX',
        
        axisLine:{
                		symbol:['none','arrow'],
                		lineStyle: {
                       color: '#fff'
                  }       		
           },
    },
   grid: {
	    		top:'15%',
	        left: '3%',
	        right: '10%',
	        bottom:'0%',
	        containLabel: true
	    },
    series: [{
        data: [0, 932, 901, 934, 1290, 1330, 1320],
        type: 'line',
        markPoint:{
						symbol: "pin", //标注类型
						symbolSize: 20 , //标记大小
						
						data:[
							{type: "max", name: "最大值"},
							{type: "min", name: "最小值"}	
						]
					},
        areaStyle: {
             normal: {
	            color: {
	                type: 'linear',//设置线性渐变
	                x: 0,
	                y: 0,
	                x2: 0,
	                y2: 1,
	                colorStops: [{
	                    offset: 0, color: '#083d8c' // 0% 处的颜色
	                }, {
	                    offset: 0.5, color: '#0b2150' // 50% 处的颜色
	                },{
	                    offset:1,color:'#0d1431'
	                }],
	                globalCoord: false // 缺省为 false
	            },
	        	}
        },
        smooth: true,
        symbol: 'none',  //取消折点圆圈

    }]
};

        myChart11.setOption(option);
	
		}
	},
	
	mounted(){
		 this.pie()
		 this.line()
		 
	}	
}


</script>

<style>
	#anaiysis-top-left-two{
		flex: 5;
		width: 300px;
		height:200px;
		padding-left: 20px;
		padding-top: 10px;
	}
</style>