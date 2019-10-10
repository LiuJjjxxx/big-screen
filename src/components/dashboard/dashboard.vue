<template lang="html">
  <div class="dashboard">
  	<hearder></hearder>
    <div class="flex-container"style="padding-top: 10px;">
        <div style="flex: 2; padding-left: 10px;">
          <warning></warning>
           <count style="margin-top: 10px;"></count>
        </div>
        <div style="flex: 6;padding-left: 10px;padding-right: 10px;">
        		<alarm></alarm>
        </div>
        <div style="float: right;flex: 2;padding-right: 16px;">
        	<notice></notice>
           <approval style="margin-top: 10px;"></approval>
        </div>
    </div>
    <div class="flex-container">
    		<div style="flex:5; padding-left: 10px;">
    			<analysis></analysis>
    		</div>
    		<div style="flex: 5; padding-left: 10px;">
    			<analysisright></analysisright>
    		</div>
    </div>
  </div>
</template>

<script>
import hearder from 'components/hearder/hearder' //大屏左上 板块一
import warning from 'components/top_left/warning' //大屏左上 板块一
import count from 'components/top_left/count' // 大屏左上 板块二
import alarm from 'components/alarm/alarm' //大屏中间 
import notice from 'components/top_right/notice' //大屏右上 板块一
import approval from 'components/top_right/approval'//大屏右上 板块二
import analysis from 'components/bottom_left/analysis'//大屏左下
import analysisright from 'components/bottom_right/analysis'//大屏左下



export default {
  data() {
    return {
      items: []
    }
  },
  mounted() {
    
  },
  methods: {
  },
  components: {
  	hearder,
    warning,
    count,
    alarm,
    notice,
    approval,
    analysis,
    analysisright,
    

  }
}

</script>

<style lang="stylus" scoped>
.dashboard
    position relative
    width 100%
    height 100%
    margin:0px;
    padding:0px;
    /*background url('../../assets/bg.jpg');*/
    background: #0a0a1c;
    background-size 100% 100%
.item
	padding-top: 10px
.flex-container
	display: flex;	
</style>