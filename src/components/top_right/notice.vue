<template>
  <div class="box">
	<div class="header">告警通知</div>
	<div class="notice">
		<ul>
			<li v-for="(item, index) in items" v-if="index < 4">
				<span>{{item.name}}</span>
				<a>{{item.where}}</a>
				{{item.msg | filterFun}}
				<span class="date">{{item.time | filterTime('-') }}</span>
			</li>
		</ul>
	</div>
	
  </div>
</template>

<script>
export default {

	data(){
		return{
			items:[
					{name:'李讯络',where:'微信',msg:'病危通知书下发报告',time: new Date()},
					{name:'刘嘉祥',where:'邮件',msg:'顶尖影视公司邀请去拍戏',time:new Date()},
					{name:'刘嘉祥',where:'钉钉',msg:'领导通知需求得重新修改',time:new Date()},
					{name:'田志强',where:'微信',msg:'微信中奖500w',time:'Tue Oct 06 2019 11:02:15'},
					{name:'黄进明',where:'微信',time:'2019-10-6'},
				],
		}	
	},
		filters: {
            filterFun: function (value) {
                if(value&& value.length > 9) {
                    value= value.substring(0,9)+'...';
                    }
                return value;
                },
            filterTime:function (time,seprator) {
                    time=new Date(time)  //看情况加
                       //3.写处理逻辑
                    let m = (time.getMonth() + 1).toString().padStart(2,'0')
                    let d = time.getDate().toString().padStart(2,'0')
                    let h = time.getHours().toString().padStart(2,'0')
                    let mm = time.getMinutes().toString().padStart(2,'0')
                    // 4 这个处理函数比如return 一个数据
                    return  m + seprator + d + ' ' + h + ':' + mm
                    }
        },

}
</script>

<style>
.notice>ul>li{
	padding-top: 20px;
	padding-left: 25px;
	text-align: left;
	color: #029de7;
}
.notice>ul>li>span{
	color: white;
}
.notice>ul>li>a{
	padding-right: 10px;
	font-size: 1px;
}
.date{
	padding-right: 20px;
	float: right;
}
</style>
