<template>
<div>
	<h1>{{sum(666)}}</h1>
</div>
</template>

<script>
	export default {
		computed: {
			sum () {
				return function (n) {
					return console.log('我是sum的参数' + n)
				}
			}
		}
	}
</script>