<template>
  <div class="box">
	<div class="header">告警事件</div>
	<div>
		<ul>
			<li v-for="(item, index) in items" v-if="index < 4"><span>【{{item.rank}}】</span>{{item.msg | filterFun}}<span class="date">{{item.time}}</span></li>
		</ul>
	</div>
	
  </div>
</template>

<script>

export default {
	data(){
		return{
			items:[
					{rank:'灾难',msg:'一群大汉闯入李讯络家,然后就那样',time:'2019-10-9'},
					{rank:'紧急',msg:'刘嘉祥越长越帅',time:'2019-10-9'},
					{rank:'普通',msg:'李讯络包皮又再生',time:'2019-10-8'},
					{rank:'未分类',msg:'外面天气很良好',time:'2019-10-7'},
					{rank:'一般',msg:'开车小心',time:'2019-10-6'},
				],
		}	
	},
		filters: {
            filterFun: function (value) {
                if(value&& value.length > 13) {
                    value= value.substring(0,13)+'...';
                    }
                return value;
                }
        },

}
</script>

<style>
ul>li{
	padding-top: 20px;
	padding-left: 25px;
	text-align: left;
	color: white;
}
ul>li>span{
	color: #049ae3;
}
.date{
	padding-right: 20px;
	float: right;
}
</style>
