<template>
    <div>
      <van-list v-model="loading"
        :finished="finished"
        finished-text="没有更多了"
        @load="onLoad"
      >
        <van-cell v-for="item in list" :key="item" :title="item" />
      </van-list>
		
		<!-- <van-tabbar v-model="active">
		  <van-tabbar-item icon="home-o">标签</van-tabbar-item>
		  <van-tabbar-item icon="search">标签</van-tabbar-item>
		  <van-tabbar-item icon="friends-o">标签</van-tabbar-item>
		  <van-tabbar-item icon="setting-o">标签</van-tabbar-item>
		</van-tabbar> -->
    </div>
</template>

<script>
	import Vue from 'vue';
	import { Tabbar, TabbarItem } from 'vant';
	import { List } from 'vant';
	
	Vue.use(List);
	Vue.use(Tabbar);
	Vue.use(TabbarItem);

	
	  
	 export default {
	   data() {
	     return {
	       list: [],
	       loading: false,
	       finished: false,
	     };
	   },
	   // created() {
	   // 		  var _this =this;
	   // 	 axios.get("http://localhost:8181/SpFlow/findAll/1/3").then(function (res) {
	   // 	                 console.log(res.data)
	   // 	                 _this.tableData = res.data.content;
	   // 	                 // _this.total = res.data.totalElements;
	   // 	 })
	   // },
	   methods: {
	     onLoad() {
	       // 异步更新数据
	       // setTimeout 仅做示例，真实场景中一般为 ajax 请求
	       setTimeout(() => {
	         for (let i = 0; i < 10; i++) {
	           this.list.push(this.list.length + 1);
	         }
	 
	         // 加载状态结束
	         this.loading = false;
	 
	         // 数据全部加载完成
	         if (this.list.length >= 40) {
	           this.finished = true;
	         }
	       }, 1000);
	     },
	   },
	 };
</script>

<style scoped>
	
</style>