<template>
	<div>
		<prism-editor
			class="my-editor height-300"
			v-model="code"
			:highlight="highlighter"
			:line-numbers="lineNumbers"
		></prism-editor>
	</div>
</template>

<script>
	import { PrismEditor } from 'vue-prism-editor'
	import 'vue-prism-editor/dist/prismeditor.min.css'
	import { highlight, languages } from 'prismjs/components/prism-core'
	import 'prismjs/components/prism-clike'
	import 'prismjs/components/prism-javascript'
	import 'prismjs/themes/prism-tomorrow.css'
	export default {
		name: 'CodeEditor1',
		components: {
			PrismEditor
		},
		data: () => ({
			code: 'console.log("Hello World");',
			lineNumbers: true // true为编辑模式， false只展示不可编辑
		}),
		methods: {
			highlighter(code) {
				return highlight(code, languages.js) //returns html
			}
		}
	}
</script>

<style lang="css" scoped>
	/* required class */
	.my-editor {
		background: #2d2d2d;
		color: #ccc;
		font-family: Fira code, Fira Mono, Consolas, Menlo, Courier, monospace;
		font-size: 14px;
		line-height: 1.5;
		padding: 5px;
	}
	/* optional */
	.prism-editor__textarea:focus {
		outline: none;
	}
	/* not required: */
	.height-300 {
		height: 300px;
	}
</style>