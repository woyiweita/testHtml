<template>
<!-- 添加事件、修改数据 -->
<div>
	<ul>
		<li v-for="(item, index) in list" v-text="item.name + ': ￥' + item.price + ' (' + item.weight + ')'" :class="{odd: index % 2}"></li>
	</ul>
	<p>
		<input type="button" value="addItem" v-on:click="addItem"><br>
		<input type="button" value="editItem" v-on:click="editItem"><br>
	</p>
</div>
</template>
<script>
	import Vue from 'vue';
	export default {
		name: 'myThree',
		data () {
			return {
				list: [
					{
						name: '洋葱',
						price: '4.90',
						weight: '500g'
					},
					{
						name: '菠菜',
						price: '6.90',
						weight: '250g'
					},
					{
						name: '生姜',
						price: '2.90',
						weight: '100g'
					},
					{
						name: '圣女果',
						price: '6.90',
						weight: '380g'
					},
					{
						name: '西红柿',
						price: '8.90',
						weight: '600g'
					},
					{
						name: '香菇',
						price: '8.50',
						weight: '250g'
					},
					{
						name: '黄瓜',
						price: '7.90',
						weight: '450g'
					},
					{
						name: '香菜',
						price: '5.90',
						weight: '150g'
					},
					{
						name: '金针菇',
						price: '2.90',
						weight: '150g'
					},
					{
						name: '土豆',
						price: '5.90',
						weight: '500g'
					},
					{
						name: '山药',
						price: '10.90',
						weight: '400g'
					}
				],
				'fruits':{
					name: '红富士苹果',
					price: '35.8',
					weight: '2400g'
				}
			}
		},
		methods:{ // 放置事件执行函数
			addItem () {
				this.list.push(this.fruits);
			},
			editItem () {
				// Vue.set(this['list'][2],'price','6.90');
				this['list'][2]['price'] = '6.90';
			}
		}
	}
</script>
<style>
	ul {padding-left: 0; list-style: none;}
	li {padding: 5px 12px; margin-bottom: 3px;}
	li.odd {color: #fff; background-color: #7dcaff;}
</style>