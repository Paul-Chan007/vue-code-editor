<template>
	<div id="app">
		<el-card>
			<Header></Header>
			<p>{{type[0]}}</p>
			<Code-Editor></Code-Editor>
			<p>{{type[1]}}</p>
			<Code-Editor1></Code-Editor1>
			<p>{{type[2]}}</p>
			<Code-Editor2
				:value="value"
				:language="language"
			></Code-Editor2>
		</el-card>
	</div>
</template>

<script>
	import Header from './components/Header.vue'
	import CodeEditor from './components/CodeEditor.vue'
	import CodeEditor1 from './components/CodeEditor1.vue'
	import CodeEditor2 from './components/CodeEditor2.vue'
	export default {
		name: 'App',
		components: {
			Header,
			CodeEditor,
			CodeEditor1,
			CodeEditor2
		},
		data() {
			return {
				value: 'console.log("Hello World");',
				language: 'Javascript',
				type: [
					'方法一：使用 vue2-ace-editor 插件实现',
					'方法二：使用 vue-prism-editor 插件实现',
					'方法三：使用 codemirror 插件实现'
				]
			}
		}
	}
</script>

<style scoped>
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		font-family: '楷体';
	}
	/deep/ .el-card {
		padding: 20px;
		margin: 20px;
	}
	p {
		margin: 20px 0;
		text-align: left;
		font-size: 20px;
		color: #409eff;
	}
</style>
