<template>
  <div id="app">
    <img class="breakpack" src="bplogo.png" />

    <p class="about-1">
      Based in Bristol, UK and Founded by Niall Shaw in 2021, Breakpack is a
      music platform for a collection of forward-thinking electronic producers,
      with the aim of connecting more likeminded individuals across the country
      from different genres, encouraging collaboration to bring out a new
      underground sound for electronic music.
    </p>
    <p class="about-2">
      Featuring artists such as short_ghost, Sunbleach, and Spheress.<br />
      <br />
      Built by Monty Anderson, Oliver Wilcox, and Oliver Redman.
    </p>
    <hr class="bio-hr" />
    <div class="releases">
      <Release v-for="r in releases" v-bind:release="r"></Release>
    </div>
  </div>
</template>

<script>
import Release from "./components/Release.vue";

export default {
  name: "App",
  components: {
    Release,
  },
  data: () => ({
    releases: [
      {
        id: "BP-001",
        title: "Mana Man",
        cover: "breakpack.png",
        date: "26/05/21",
        artist: "Shortghost",
        type: "Single",
        spotifylink: "https://open.spotify.com/album/3kUDCESgS3cT2zBUPpKIlS",
        bandcamplink: "https://shortghost.bandcamp.com/album/mana-man",
        track: "",
      },
      
    ],
  }),
};
</script>

<style>
#app {
  position: absolute;
  transform: translateX(-50%);
  left: 50%;
  top: 00px;
}

.breakpack {
  position: relative;
  margin-top: 40px;
  width: 200px;
  left: 50%;
  transform: translateX(-50%);
}

h1 {
  position: absolute;
  width: 268px;
  height: 43px;
  left: 52px;

  font-family: Rubik Mono One;
  font-style: normal;
  font-weight: normal;
  font-size: 35px;
  line-height: 43px;

  color: #ffffff;
}

.about-1 {
  position: relative;
  width: 319px;
  height: 126px;
  left: 50%;
  transform: translateX(-50%);
  margin-top: 40px;

  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 14px;
  text-align: justify;

  color: #ffffff;
}

.about-2 {
  position: relative;
  width: 319px;

  left: 50%;
  transform: translateX(-50%);
  margin-top: -15px;

  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;

  text-align: justify;

  color: #ffffff;
}

.bio-hr {
  position: relative;
  width: 95px;
  height: 0px;

  margin-top: 40px;
  left: 50%;
  transform: translateX(-50%);
  border: 2px solid #ffffff;
}

.releases {
  position: relative;
  display: flex;
  flex-direction: column;
  margin-top: 90px;
  height: auto;
  left: 50%;
  transform: translateX(-50%);
  width: 80vw;
}

@media screen and (min-width: 750px) {
  .breakpack {
    left: 1%;

    top: 3vw;
    transform: none;
    width: 30vw;
  }
  .about-1 {
    width: 29vw;
    font-size: 1vw;
    left: calc(100% - 31vw);
    transform: none;
    margin-top: -17vw;
    height: 5vw;
    line-height: 1.4vw;
  }
  .about-2 {
    width: 29vw;
    font-size: 1vw;
    left: calc(100% - 31vw);
    transform: none;
    margin-top: 6vw;

    height: 5vw;
    line-height: 1.4vw;
  }
  .bio-hr {
    display: none;
  }

  .releases {
    position: relative;
    margin-top: 13vw;
    width: 70vw;
  }
}
</style>
