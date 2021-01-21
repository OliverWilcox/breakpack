<template>
	<div class="release" v-bind:class="{ open }" v-on:click="open = !open">
		<hr>
		<p class="id">{{id}}</p>
		<p class="title">{{title}}</p>
		<img class="cover" v-bind:src="cover">
		<p class="date" v-if="open === true">{{date}}</p>
		<p class="artist" v-if="open === true">{{artist}}</p>
		<p class="Type" v-if="open === true">{{type}}</p>
		<img class="big-cover" v-bind:src="cover" v-if="open === true">
		<div class="play" v-if="open === true">
		<div class="line"></div>
		<p class="title" v-if="open === true">{{title}}</p>
		<p class="playbtn"><i class="fas fa-play"></i></p>
		<p class="spotifybtn" v-on:click="spotifyOpen()"><i class="fab fa-spotify"></i></p>
		<p class="bandcampbtn"><i class="fab fa-bandcamp" v-on:click="bandcampOpen()"></i></p>
		</div>
	</div>
</template>

<script>
export default {
	props: [
		'id',
		'title',
		'cover',
		'date',
		'artist',
		'type',
		'spotifylink',
		'bandcamplink'
	],
	data: () => ({
		open: false
	}),
	methods:{
		spotifyOpen(){
         window.location = this.spotifylink;
		},
		bandcampOpen(){
         window.location = this.bandcamplink
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

.artist{
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

.Type{
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

.line{
	left:54px;
	background-color: black;
    width: 1px;
	height: 38px;
	position: absolute;
	top: 9px;
}

.playbtn{
position:absolute;
top: 15px;	
left: 19px;
font-size: 22px;
}

.spotifybtn{
	position:absolute;
top: 15px;	
left: 245px;
font-size: 22px;
}

.bandcampbtn{
	position:absolute;
top: 15px;	
left: 275px;
font-size: 22px;
}

.big-cover {
	position: absolute;
	width: 313px;
	left: 30px;
	top: 225px;	
}
</style>
