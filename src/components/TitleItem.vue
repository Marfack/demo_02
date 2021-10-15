<template>
  <div class="box">
		<div class="font">
			<span>{{target.name}}</span>
		</div>
		<div class="font">
			<span>{{target.value}}</span>
		</div>
	</div>
</template>

<script>
export default {
	name: "TitleItem",
	props: {
		target: Object
	}
}
</script>

<style scoped>
.font {
	padding: 20px;
	margin: auto;
	text-align: center;
	color: #343434;
	font-weight: normal;
	font-family: 'Ultra', sans-serif;   
	font-size: 25px;
	text-transform: uppercase;
	text-shadow: 0 -1px 1px rgba(0,0,0,0.4);
}
</style>