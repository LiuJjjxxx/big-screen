<template>
	<div class="header-all">
		<div class="hearder-date header-color">
			<ul>
	            <li v-for='(item,index) in list' v-if="index < 1">
	                {{years}}-{{item.date}}       
	            </li>
            </ul>
		</div>
		<div class="header-font header-color">神州动力数码大数据平台</div>
		<div class="header-right loc"></div>
		<div class="header-left loc"></div>
		<div class="hearder-weather header-color">
			<ul>
	            <li v-for='(item,index) in list' v-if="index < 1">
	                <!-- 通过v-if-else 判断是否存在某个字段 -->
			            	<span v-if='item.type.indexOf("云")!=-1'>🌥️</span>
			            <span v-else-if='item.type.includes("雷阵雨")'>⛈️</span>
			            <span v-else-if='item.type.includes("雨")!=-1'>🌧️</span>
			            <span v-else>🌞</span> 
	                {{item.type}}-{{item.high}}-{{item.low}}         
	            </li>
            </ul>
        </div>
  	</div>
</template>

<script>
	import $ from '../../assets/js/jquery-vendor.js';
	 export default{
        data(){
        		return{
        			years:new Date().getFullYear()+'-'+new Date().getMonth	(),
	            msg:'',
	            list:[]
           }
        },
        methods: {
        },
         mounted(){
                //发送ajax请求
                $.ajax({
                    type:'get',
                    url:'http://wthrcdn.etouch.cn/weather_mini?city=深圳',
                    data:{
                        // msg在vue实例对象中 所以要用this点出来
                        city:this.msg
                    },
                    //因为返回的是json格式的字符串 可以通过dataType转js对象
                    dataType:'json',
                    success:(backData)=>{

                        //通过打印的结果 可以通过数组渲染到页面上
                        this.list=backData.data.forecast;    
                    }
                })
            }
	 }
</script>

<style>
.header-all{
	position:relative;
	display:inner-block;
	height:100px;
	background-image:linear-gradient(to right, #0F0F0F 10% ,#0e254e 60%  ,#0F0F0F  );
	}
.header-left{

	border-bottom: 40px solid #0a0a1c; 
	border-right: 100px solid transparent;
	}
.header-right{
	right:0px;
	border-bottom: 40px solid #0a0a1c; 
	border-left: 100px solid transparent;
	}
.loc{
	position:absolute;
	height: 0; width: 500px;
	transform:translateY(60px);
	display:inline-block;
}
.header-color{
	position:absolute;
	color:white;
	font-size:30px;
}
.hearder-date{
	font-size: 25px;
}
.header-font{
	text-shadow:#0090fe 3px 0px 4px;
	margin: auto;
	z-index:10;
	display: inline;
	top:5vh;
	left:70vh;
	}
.header-font:before{
	text-shadow:transparent 0 1px 0;
	content:'Szpdc';
	padding-right:10px;
	font-family:fantasy;
	}
.hearder-weather{
	right: 0;
	font-size: 25px;
}
</style>