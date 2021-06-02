<template>
  <div class="release" v-bind:class="{ open }">
    <hr />

    <div>
      <p class="id">{{ release.id }}</p>
      <p class="title" v-on:click="open = !open">{{ release.title }}</p>
      <img class="cover" v-bind:src="release.cover" />
    </div>

    <audio class="playtest" ref="player" v-bind:src="release.track"></audio>

    <div class="opencontainer" v-if="open === true">
      <p class="date">{{ release.date }}</p>
      <p class="artist">{{ release.artist }}</p>
      <p class="Type">{{ release.type }}</p>

      <img class="big-cover" v-bind:src="release.cover" />

      <div class="play">
        <input
          type="range"
          class="progress-bar"
          min="0"
          max="100"
          :value="inputCurrentTime"
          ref="prog"
          v-on:input="changeProgress()"
          step="0.1"
        />

        <div class="time-left">{{ timeleft }}</div>
        <div class="line"></div>
        <div class="title-cont">
          <p class="title-copy" ref="title">{{ release.title }}</p>
        </div>

        <p class="playbtn">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="35"
            height="35"
            fill="currentColor"
            class="bi bi-pause-fill"
            viewBox="0 0 16 16"
            v-if="playing === true"
            v-on:click="pause"
          >
            <path
              d="M5.5 3.5A1.5 1.5 0 0 1 7 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5zm5 0A1.5 1.5 0 0 1 12 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5z"
            />
          </svg>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="35"
            height="35"
            fill="currentColor"
            class="bi bi-play-fill"
            viewBox="0 0 16 16"
            v-else
            v-on:click="play"
          >
            <path
              d="M11.596 8.697l-6.363 3.692c-.54.313-1.233-.066-1.233-.697V4.308c0-.63.692-1.01 1.233-.696l6.363 3.692a.802.802 0 0 1 0 1.393z"
            />
          </svg>
        </p>
      </div>
      <a class="spotifybtn" v-bind:href="release.spotifylink" target="_blank">
        <i class="fab fa-spotify"></i>
      </a>

      <a class="bandcampbtn" v-bind:href="release.bandcamplink" target="_blank">
        <i class="fab fa-bandcamp"></i>
      </a>
    </div>
  </div>
</template>

<script>
//import track from "../yesterday.mp3"
export default {
  props: ["release"],
  data: () => ({
    open: false,
    playing: false,
    inputCurrentTime: 0,
    timeleft: 0,
  }),
  mounted() {
    window.setInterval(() => {
      this.setProgress();
    }, 500);
  },
  computed: {
    progress() {},
  },
  methods: {
    play() {
      this.$refs.player.play();
      this.playing = true;
      this.$refs.title.style.animationPlayState = "initial";
    },
    pause() {
      this.$refs.player.pause();
      this.playing = false;
      this.$refs.title.style.animationPlayState = "paused";
    },
    changeProgress() {
      let audioTime =
        (this.$refs.prog.value / 100) * this.$refs.player.duration;
      this.$refs.player.currentTime = audioTime;
    },

    setProgress() {
      this.inputCurrentTime =
        (this.$refs.player.currentTime / this.$refs.player.duration) * 100;
      let audiotimeleft =
        this.$refs.player.duration - this.$refs.player.currentTime;

      let minutes = `${Math.floor(audiotimeleft / 60)}`;

      if (minutes.length === 1) {
        minutes = `0${minutes}`;
      }

      let seconds = `${Math.floor(audiotimeleft % 60)}`;
      if (seconds.length === 1) {
        seconds = `0${seconds}`;
      }
      this.timeleft = `${minutes}:${seconds}`;
    },
  },
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
}

.release hr {
  position: absolute;
  width: 309px;
  height: 0px;
  left: 0px;
  top: 0px;

  border: 2px solid #ffffff;
}

.id {
  position: absolute;
  width: 80px;
  height: 24px;
  left: 0px;
  top: 26px;

  font-family: Rubik;
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 24px;

  color: #ffffff;
}

.title,
.title-copy {
  position: absolute;
  width: 162px;
  height: 24px;
  left: 89px;
  top: 26px;

  font-family: Rubik;
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 24px;

  color: #ffffff;
}
.title {
  cursor: pointer;
}

.cover {
  position: absolute;
  width: 30px;
  height: 30px;
  right: 0;
  top: 20px;
}

.date {
  position: absolute;
  width: 41px;
  height: 19px;
  left: 0px;
  top: 90px;

  font-family: Rubik;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  /* identical to box height */

  color: #ffffff;
}

.artist {
  position: absolute;
  width: 84px;
  height: 19px;
  left: 90px;
  top: 90px;
  font-family: Rubik;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #ffffff;
}

.Type {
  position: absolute;

  right: 0;
  top: 90px;
  font-family: Rubik;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #ffffff;
}

.play {
  position: absolute;
  width: 313px;
  height: 64px;
  left: 0px;
  top: 143px;

  background: #ffffff;
}

.title-cont {
  position: absolute;
  left: 58px;
  width: 56px;
  height: 30px;
  background: rgb(255, 255, 255);
  overflow: hidden;
}

.play .title,
.play .title-copy {
  top: 50%;
  transform: translateY(-50%);
  color: black;
  left: 10%;
  font-size: 18px;
  animation: scrollText 3s infinite linear;
  animation-play-state: paused;
}

@keyframes scrollText {
  from {
    left: 10%;
  }
  to {
    left: -200%;
  }
}

.line {
  left: 54px;
  background-color: black;
  width: 1px;
  height: 38px;
  position: absolute;
  top: 13px;
}

.playbtn {
  position: absolute;
  top: 15px;
  left: 11px;
  width: 100px;
  height: 100px;
  color: black;
}
.bi {
  cursor: pointer;
}

.playbtn .open #pause {
  display: block;
}

.spotifybtn {
  position: absolute;
  top: 540px;
  left: 0px;
  font-size: 24px;
  color: #1db954;
  height: 50px;
}

.bandcampbtn {
  position: absolute;
  top: 540px;
  left: 30px;
  font-size: 24px;
  color: #629aa9;
}

.big-cover {
  position: absolute;
  width: 313px;
  left: 0px;
  top: 235px;
}

.progress-bar {
  -webkit-appearance: none;
  appearance: none;
  position: absolute;

  background: #131313;

  z-index: +1;
  position: relative;
  position: relative;
  top: 20px;
  left: 120px;
  width: 170px;
}

.progress-bar::-webkit-slider-thumb {
  cursor: pointer;
  -webkit-appearance: none;
  margin-top: -3px;
  margin-left: 0px;
  height: 9px;
  width: 9px;
  border: 0;

  background: black;
  border-radius: 30px;
  cursor: pointer;
}
.progress-bar::-webkit-slider-runnable-track {
  appearance: none;

  cursor: pointer;
  max-height: 3px;
}
.progress-bar:focus {
  outline: none;
  outline: none;
}

.time-left {
  position: absolute;
  bottom: 10px;
  right: 22px;
  font-size: 11px;
  color: black;
  font-family: Rubik;
}
</style>
