<template>
	<div>
		<h2>{{title}}</h2>
	</div>
</template>

<script>
	export default {
		name: 'Header',
		data() {
			return {
				title: 'VUE 项目中嵌入代码编辑器示例'
			}
		}
	}
</script>

<style lang="css" scoped>
	div {
		margin-bottom: 20px;
		text-align: center;
		color: #f56c6c;
	}
</style>