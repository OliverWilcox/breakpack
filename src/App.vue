<template>
	<div id="app">
		<h1>breakpack</h1>
        <hr>
		<p class="about-1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras et purus eu quam luctus imperdiet ut eget nisl. Fusce non orci tincidunt, egestas mi non, blandit massa. Proin ac enim dictum sem auctor malesuada a ut nulla. Morbi quis lectus consectetur, imperdiet elit eu, vehicula mauris. In hac habitasse platea dictumst. Etiam varius dapibus sagittis. Cras molestie vulputate justo, non facilisis urna iaculis sit amet. Etiam efficitur diam vitae semper auctor.</p>
		<p class="about-2">Donec aliquet dignissim tortor, eu efficitur nisl rhoncus et. Nullam orci odio, venenatis sed eleifend ac, commodo quis justo. Vestibulum mattis tristique pharetra. Nunc quis orci porta, ultricies nibh ut, sollicitudin massa. Nunc consectetur neque vel quam fringilla.</p>
	  	<div class="releases">
		  	<Release v-for="r in releases"   v-bind:releases="releases" v-bind:id="r.id" v-bind:title="r.title" v-bind:cover="r.cover" v-bind:date="r.date" v-bind:artist="r.artist" v-bind:type="r.type" v-bind:spotifylink="r.spotifylink" v-bind:bandcamplink="r.bandcamplink" v-bind:track="r.track"></Release>
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
			  id: 'BP-003',
			  title: 'world massive',
			  cover: 'https://f4.bcbits.com/img/a1714057810_10.jpg',
			  date: '12/07/21',
			  artist: 'Shortghost',
              type: 'EP',
			  spotifylink: 'https://open.spotify.com/album/3JBPcjSVKwCaUltFKBIPs7',
			  bandcamplink: 'https://shortghost.bandcamp.com/album/xx-xx-2',
			  track: "https://t4.bcbits.com/stream/c1dcdb689aefb8a7c0e5f92c0894c918/mp3-128/3089568016?p=0&ts=1611411481&t=d9d53628a11d05aec32523cc8acbfbcb5bda83ec&token=1611411481_5f78858d7fe9febec4a0ae2a73903878c4b7292f"
		  },
		  {
			  id: 'BP-002',
			  title: 'XX_XX',
			  cover: 'https://f4.bcbits.com/img/a0124850087_10.jpg',
			  date: '12/07/21',
			  artist: 'Shortghost',
              type: 'EP',
			  spotifylink: 'https://open.spotify.com/album/3JBPcjSVKwCaUltFKBIPs7',
			  bandcamplink: 'https://shortghost.bandcamp.com/album/xx-xx-2',
			  track: 'https://t4.bcbits.com/stream/c5371336d45d85b5111554a3f59de48b/mp3-128/812403648?p=0&ts=1611411241&t=aade02bf4139519574ef1248176154e2f902ee55&token=1611411241_7e3024f510964a83505268be47638b29b8d34607'
		  },
		  {
			  id: 'BP-001',
			  title: 'XX_XX',
			  cover: 'https://f4.bcbits.com/img/a0124850087_10.jpg',
			  date: '12/07/21',
			  artist: 'Shortghost',
              type: 'EP',
			  spotifylink: 'https://open.spotify.com/album/3JBPcjSVKwCaUltFKBIPs7',
			  bandcamplink: 'https://shortghost.bandcamp.com/album/xx-xx-2',
			  track: 'https://t4.bcbits.com/stream/720bc5443ec2189be4e03291b9fe36bb/mp3-128/3287546992?p=0&ts=1611410738&t=bb1dab995f2caa7003e0a997ff8f0e98cb67eb17&token=1611410738_17d741b5d6d47ceac7b593f4d8637091419696bd'
		  }
	  ],
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
	height: auto;
}
</style>
