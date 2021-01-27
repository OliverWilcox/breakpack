<template>
	<div class="release" v-bind:class="{ open }">
		<hr>

		<div >

			<p class="id" >{{release.id}}</p>
			<p class="title" v-on:click="open = !open">{{release.title}}</p>
			<img class="cover" v-bind:src="release.cover">
		</div>

		<audio class="playtest" ref="player" v-bind:src="release.track"></audio>

		<div class="opencontainer" v-if="open === true">
			<p class="date">{{release.date}}</p>
			<p class="artist">{{release.artist}}</p>
			<p class="Type">{{release.type}}</p>

			<img class="big-cover" v-bind:src="release.cover">

			<div class="play">
				<div class="line"></div>
				<p class="title">{{release.title}}</p>

				<p class="playbtn">
					<svg xmlns="http://www.w3.org/2000/svg" width="35" height="35" fill="currentColor" class="bi bi-pause-fill" viewBox="0 0 16 16" v-if="playing === true" v-on:click="pause">
  <path d="M5.5 3.5A1.5 1.5 0 0 1 7 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5zm5 0A1.5 1.5 0 0 1 12 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5z"/>
</svg>
					<svg xmlns="http://www.w3.org/2000/svg" width="35" height="35" fill="currentColor" class="bi bi-play-fill" viewBox="0 0 16 16" v-else v-on:click="play">
  <path d="M11.596 8.697l-6.363 3.692c-.54.313-1.233-.066-1.233-.697V4.308c0-.63.692-1.01 1.233-.696l6.363 3.692a.802.802 0 0 1 0 1.393z"/>
</svg>
				</p>

				<a class="spotifybtn" v-bind:href="release.spotifylink">
					<i class="fab fa-spotify"></i>
				</a>

				<a class="bandcampbtn" v-bind:href="release.bandcamplink">
					<i class="fab fa-bandcamp"></i>
				</a>
			</div>
		</div>

	</div>
</template>

<script>
export default {
	props: [
		'release'
	],
	data: () => ({
		open: false,
		playing: false
	}),
	methods: {
		play() {
			this.$refs.player.play();
			this.playing = true;
		},
		pause() {
			this.$refs.player.pause();
			this.playing = false;
		}
	}
};
</script>

<style>
.release {
	height: 74px;
	position: relative;
	transition: 0.2s;
}

.release.open {
	height: 575px;
	transition: 0.2s;
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
	width: 80px;
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

.date{
	position: absolute;
	width: 41px;
	height: 19px;
	left: 30px;
	top: 90px;

	font-family: Rubik;
	font-style: normal;
	font-weight: 500;
	font-size: 16px;
	line-height: 19px;
	/* identical to box height */

	color: #FFFFFF;
}

.artist {
	position: absolute;
	width: 84px;
	height: 19px;
	left: 126px;
	top: 90px;
	font-family: Rubik;
	font-style: normal;
	font-weight: 500;
	font-size: 16px;
	line-height: 19px;
	color: #FFFFFF;
}

.Type {
	position: absolute;
	width: 84px;
	height: 19px;
	left: 318px;
	top: 90px;
	font-family: Rubik;
	font-style: normal;
	font-weight: 500;
	font-size: 16px;
	line-height: 19px;
	color: #FFFFFF;
}

.play{
	position: absolute;
	width: 313px;
	height: 54px;
	left: 31px;
	top: 143px;

	background: #FFFFFF;
}

.play .title{
	top: 15px;
    color: black;
	left: 75px;
	font-size: 18px;

}

.line {
	left:54px;
	background-color: black;
	width: 1px;
	height: 38px;
	position: absolute;
	top: 9px;
}

.playbtn{
	position:absolute;
	top: 10px;
	left: 11px;
	width: 100px;
	height: 100px;
	color: black;

}

.playbtn .open #pause{
	display: block;
}

.spotifybtn {
	position:absolute;
	top: 15px;
	left: 245px;
    font-size: 22px;
	color: #1DB954;
}

.bandcampbtn {
	position:absolute;
	top: 15px;
	left: 275px;
	font-size: 22px;
	color: #629aa9;
}

.big-cover {
	position: absolute;
	width: 313px;
	left: 30px;
	top: 225px;
}
</style>
