<template>
	<div id="app">
		<h1>breakpack</h1>

		<p class="about-1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras et purus eu quam luctus imperdiet ut eget nisl. Fusce non orci tincidunt, egestas mi non, blandit massa. Proin ac enim dictum sem auctor malesuada a ut nulla. Morbi quis lectus consectetur, imperdiet elit eu, vehicula mauris. In hac habitasse platea dictumst. Etiam varius dapibus sagittis. Cras molestie vulputate justo, non facilisis urna iaculis sit amet. Etiam efficitur diam vitae semper auctor.</p>
		<p class="about-2">Donec aliquet dignissim tortor, eu efficitur nisl rhoncus et. Nullam orci odio, venenatis sed eleifend ac, commodo quis justo. Vestibulum mattis tristique pharetra. Nunc quis orci porta, ultricies nibh ut, sollicitudin massa. Nunc consectetur neque vel quam fringilla.</p>

		<hr></hr>

	  	<div class="releases">
		  	<Release v-for="r in releases" v-bind:id="r.id" v-bind:title="r.title" v-bind:cover="r.cover"></Release>
	  	</div>
	</div>
</template>

<script>
import Release from './components/Release.vue';

export default {
  name: 'App',
  components: {
	  Release
  },
  data: () => ({
	  releases: [
		  {
			  id: 'BP-02',
			  title: 'world massive',
			  cover: 'https://f4.bcbits.com/img/a1714057810_10.jpg'
		  },
		  {
			  id: 'BP-01',
			  title: 'XX_XX',
			  cover: 'https://f4.bcbits.com/img/a0124850087_10.jpg'
		  }
	  ]
  })
}
</script>

<style>
#app {
	width: 375px;
	background: black;
}

h1 {
	position: absolute;
	width: 268px;
	height: 43px;
	left: 52px;
	top: 108px;

	font-family: Rubik Mono One;
	font-style: normal;
	font-weight: normal;
	font-size: 35px;
	line-height: 43px;

	color: #FFFFFF;
}

.about-1 {
	position: absolute;
	width: 319px;
	height: 126px;
	left: 28px;
	top: 181px;

	font-family: Rubik;
	font-style: normal;
	font-weight: normal;
	font-size: 12px;
	line-height: 14px;
	text-align: justify;

	color: #FFFFFF;
}

.about-2 {
	position: absolute;
	width: 319px;
	height: 70px;
	left: 28px;
	top: 328px;

	font-family: Rubik;
	font-style: normal;
	font-weight: normal;
	font-size: 12px;
	line-height: 14px;
	text-align: justify;

	color: #FFFFFF;
}

hr {
	position: absolute;
	width: 95px;
	height: 0px;
	left: 139px;
	top: 464px;

	border: 2px solid #FFFFFF;
}

.releases {
	position: absolute;
	top: 538px;
}
</style>
