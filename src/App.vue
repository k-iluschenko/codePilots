<template>
  <div id="app">
    <Animation />
  </div>
</template>

<script>
import Animation from "./components/Animation";

export default {
  name: "app",
  components: {
    Animation
  }
};
</script>

<style lang="scss">
@font-face {
  font-family: "Cocogoose Compressed Trial Regular";
  src: url("./assets/fonts/CocogooseCompressedTrial-Regula.eot?") format("eot"),
    url("./assets/fonts/CocogooseCompressedTrial-Regula.woff") format("woff"),
    url("./assets/fonts/CocogooseCompressedTrial-Regula.ttf") format("truetype"),
    url("./assets/fonts/CocogooseCompressedTrial-Regula.svg#CocogooseCompressedTrial-Regula")
      format("svg");
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "FavoritCondC";
  src: url("./assets/fonts/FavoritCondC.eot");
  src: url("./assets/fonts/FavoritCondC.eot?#iefix") format("embedded-opentype"),
    url("./assets/fonts/FavoritCondC.woff2") format("woff2"),
    url("./assets/fonts/FavoritCondC.woff") format("woff"),
    url("./assets/fonts/FavoritCondC.ttf") format("truetype"),
    url("./assets/fonts/FavoritCondC.svg#FavoritCondC") format("svg");
  font-weight: normal;
  font-style: normal;
}
@font-face {
  font-family: "Roboto Condensed";
  src: url("./assets/fonts/Robotocondensed.woff2") format("woff2"),
    url("./assets/fonts/Robotocondensed.woff") format("woff"),
    url("./assets/fonts/Robotocondensed.ttf") format("truetype");
  font-weight: 400;
  font-style: normal;
}

#app {
  font-family: "FavoritCondC", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #222222;
  height: 100%;
}
html,
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-size: 18px;
  height: 100%;
}

a {
  text-decoration: none;
  color: #222222;
  & :hover,
  :active {
    color: #222222;
    text-decoration: none;
  }
}
</style>
