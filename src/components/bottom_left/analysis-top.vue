<template>
		<div style="display: flex;">
				<div id="anaiysis-top-left"></div>
				<div id="anaiysis-top-right" style="width: 300px;height: 200px; flex: 5;"></div>
		</div>
</template>

<script>
import echarts from 'echarts'
export default {
	methods:{
		pie(){

			var myChart = echarts.init(document.getElementById('anaiysis-top-left'),'blue-science');
        // 指定图表的配置项和数据
        var option = {
        	backgroundColor:'', //设置无背景色
	    tooltip : {
	        trigger: 'item',
	        formatter: "{a} <br/>{b} : {c} ({d}%)"
	    },
		graphic: [
	        {
	            type: 'image',
	            id: 'logo',
	            left: 'left',
	            top: 'center',
	            z: -10,
	            bounding: 'raw',
	            origin: [75, 75],
	            style: {
	                image: '../static/img/chartbk.png',
	                width: 200,
	                height: 200,
	                opacity: 0.8
	            }
	        },
	    ],
	    visualMap: {
	        show: false,
	        min: 80,
	        max: 600,
	        inRange: {
	            colorLightness: [0, 1]
	        }
	    },
	    legend: {
	    	textStyle:{//图例文字的样式
            color:'#ccc',
        },
		orient: 'vertical',
	        x : '250',
	    		y : 'center',
	        data:['直接访问','邮件营销','联盟广告','视频广告','搜索引擎']
	    },
	    series : [
	        {
	            name:'访问来源',
	            type:'pie',
	            radius : '55%',
	            center: ['25%', '50%'],
	            data:[
	                {value:335, name:'直接访问'},
	                {value:310, name:'邮件营销'},
	                {value:274, name:'联盟广告'},
	                {value:235, name:'视频广告'},
	                {value:400, name:'搜索引擎'}
	            ].sort(function (a, b) { return a.value - b.value; }),
	            roseType: 'radius',
	            label: {
	                normal: {
	                    show:false,
	                }
	            },
	            labelLine: {
	                normal: {
	                    lineStyle: {
	                        color: 'rgba(255, 255, 255, 0.3)'
	                    },
	                    smooth: 0.2,
	                    length: 10,
	                    length2: 20
	                }
	            },           
	            itemStyle: {
	                normal: {
//	                    color: 'rgb(5,39,175)',
	                    shadowBlur: 200,
	                    shadowColor: 'rgba(0, 0, 0, 0.5)'
	                }
	            },
	
	            animationType: 'scale',
	            animationEasing: 'elasticOut',
	            animationDelay: function (idx) {
	                return Math.random() * 200;
	            }
	        }
	    ]
	};
	var rotation = 0;
        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);

		},
	line(){
		var myChart11 = echarts.init(document.getElementById('anaiysis-top-right'),'purple-passion');
		
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
	        right: '15%',
	        bottom:'0%',
	        containLabel: true
	    },
	 
	    xAxis : [
	        {
	            type : 'category',
	            data : ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'],
	            axisTick: {
	                alignWithLabel: true,
	                
	            },
	            axisLabel:{
	            		
	            }
	            
	            
	            
	        }
	    ],
	    yAxis : [
	        {
	            type : 'value',
	            axisLabel:{
	            		textStyle: {
                                color: '#fff'
                           },
	            },
	            axisLine:{
                		symbol:['none','arrow']                         
            },
	            
	        }
	        
	    ],
	    series : [
	        {
	        	markLine : {
							label:{	
								formatter:'指标线',
//								position:"end"          //将警示值放在哪个位置，三个值“start”,"middle","end"  开始  中点 结束
								show:true
							},
                            data : [{
								silent:false,             //鼠标悬停事件  true没有，false有
								lineStyle:{               //警戒线的样式  ，虚实  颜色
                                    type:"dashed",
									color:"#72fff6",
								},
								yAxis:210           // 警戒线的标注值，可以有多个yAxis,多条警示线   或者采用   {type : 'average', name: '平均值'}，type值有  max  min  average，分为最大，最小，平均值
							}]
                        },
	        		itemStyle: {
                normal: { 
               		label: {
				          show: true,
				          position: 'top',
				          textStyle: {
				            color: 'white'
				      	}
			          },
                    color: new echarts.graphic.LinearGradient(
                        0, 0, 0, 1,
                        [
                            {offset: 0, color: '#274efe'},
                            {offset: 0.5, color: '#377af4'},
                            {offset: 1, color: '#188df0'}
                        ]
                    )
                },
                emphasis: {
                    color: new echarts.graphic.LinearGradient(
                        0, 0, 0, 1,
                        [
                            {offset: 0, color: '#188df0'},
                            {offset: 0.7, color: '#377af4'},
                            {offset: 1, color: '#274efe'}
                        ]
                    )
                }
            },
	            name:'直接访问',
	            type:'bar',
	            barWidth: '60%',
	            data:[10, 52, 200, 334, 390, 330]
	        }
	    ]
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
	#anaiysis-top-left{
		flex: 5;
		width: 300px;
		height:200px;
		padding-left: 20px;
		padding-top: 10px;
	}
</style>