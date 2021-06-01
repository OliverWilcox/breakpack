<template>
	<div id="app">
		<img class="breakpack" src="bplogo.png"/>

        <hr>
		<p class="about-1">Based in Bristol, UK and Founded by Niall Shaw in 2021, Breakpack is a music platform for a collection of forward-thinking electronic producers, with the aim of connecting more likeminded individuals across the country from different genres, encouraging collaboration to bring out a new underground sound for electronic music.</p>
        <p class="about-2"> Featuring artists such as short_ghost, Sunbleach, and Spheress.<br>
		<br>
Built by Monty Anderson, Oliver Wilcox, and Oliver Redman.</p>
	  	<div class="releases">
		  	<Release v-for="r in releases" v-bind:release="r"></Release>
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
			  id: 'BP-001',
			  title: 'Mana Man',
			  cover: 'breakpack.png',
			  date: '26/05/21',
			  artist: 'Shortghost',
              type: 'Single',
			  spotifylink: 'https://open.spotify.com/album/3kUDCESgS3cT2zBUPpKIlS',
			  bandcamplink: 'https://shortghost.bandcamp.com/album/mana-man',
			  track: "https://t4.bcbits.com/stream/c1dcdb689aefb8a7c0e5f92c0894c918/mp3-128/3089568016?p=0&ts=1611411481&t=d9d53628a11d05aec32523cc8acbfbcb5bda83ec&token=1611411481_5f78858d7fe9febec4a0ae2a73903878c4b7292f"
		  },
	  ]
  })
}
</script>

<style>
#app {
	width: 375px;
	min-height: 800px;
	position: absolute;
	transform: translate(-50%, -50%);
	left: 50%;
	top: 400px;
}

.breakpack{
	position: absolute;
	top: 40px;
	width: 200px;
	left: 50%;
	transform: translateX(-50%);
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
	top: 231px;

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
	top: 355px;

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
	top: 514px;

	border: 2px solid #FFFFFF;
}

.releases {
	position: absolute;
	top: 578px;
	height: auto;
	left: 50%;
	transform: translateX(-50%);
width: 313px;
	height: 50px;
	
}


</style>
