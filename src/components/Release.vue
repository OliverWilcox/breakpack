<template>
	<div class="release" v-bind:class="{ open }" v-on:click="open = !open">
		<hr>

		<p class="id">{{id}}</p>
		<p class="title">{{title}}</p>
		<img class="cover" v-bind:src="cover">

		<img class="big-cover" v-bind:src="cover" v-if="open === true">
	</div>
</template>

<script>
export default {
	props: [
		'id',
		'title',
		'cover'
	],
	data: () => ({
		open: false
	})
};
</script>

<style>
.release {
	height: 74px;
	position: relative;
}

.release.open {
	height: 450px;
}

.release hr {
	position: absolute;
	width: 313px;
	height: 0px;
	left: 30px;
	top: 0px;

	border: 2px solid #FFFFFF;
}

.id {
	position: absolute;
	width: 61px;
	height: 24px;
	left: 30px;
	top: 26px;

	font-family: Rubik;
	font-style: normal;
	font-weight: 500;
	font-size: 20px;
	line-height: 24px;

	color: #FFFFFF;
}

.title {
	position: absolute;
	width: 162px;
	height: 24px;
	left: 119px;
	top: 26px;

	font-family: Rubik;
	font-style: normal;
	font-weight: 500;
	font-size: 20px;
	line-height: 24px;

	color: #FFFFFF;
}

.cover {
	position: absolute;
	width: 30px;
	height: 30px;
	left: 307px;
	top: 20px;
}

.big-cover {
	position: absolute;
	width: 313px;
	left: 30px;
	top: 101px;
}
</style>
