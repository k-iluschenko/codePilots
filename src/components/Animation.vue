<template>
  <div>
    <div class="main-background min-width">
      <Header />
      <div id="menu-background" class="faded">
        <div id="menu-background-image" :class="{ hidden: hidden }">
          <MainPage :isShow="isShow" />
        </div>
        <div id="menu-background-image-new" :class="{ visible: !hidden }">
          <MainPage />
        </div>
      </div>
    </div>

    <div id="grid" class="row min-width" :style="{ 'z-index': zIndex }">
      <div
        :class="{
          'background-closed': backgroundClosed,
          'background-open': backgroundOpen
        }"
        class="col"
      >
        <div class="grid-line" style="transition-duration: 0.9s;"></div>
        <div class="grid-background"></div>
      </div>

      <div
        :class="{
          'background-closed': backgroundClosed,
          'background-open': backgroundOpen
        }"
        class="col"
      >
        <div class="grid-line" style="transition-duration: 0.9s;"></div>
        <div class="grid-background"></div>
      </div>

      <div
        :class="{
          'background-closed': backgroundClosed,
          'background-open': backgroundOpen
        }"
        class="col"
      >
        <div class="grid-line" style="transition-duration: 0.5s;"></div>
        <div class="grid-background"></div>
      </div>

      <div
        :class="{
          'background-closed': backgroundClosed,
          'background-open': backgroundOpen
        }"
        class="col"
      >
        <div class="grid-line" style="transition-duration: 0.8s;"></div>
        <div class="grid-background"></div>
      </div>

      <div
        :class="{
          'background-closed': backgroundClosed,
          'background-open': backgroundOpen
        }"
        class="col"
      >
        <div class="grid-line" style="transition-duration: 1.2s;"></div>
        <div class="grid-background"></div>
      </div>

      <div
        :class="{
          'background-closed': backgroundClosed,
          'background-open': backgroundOpen
        }"
        class="col"
      >
        <div class="grid-line" style="transition-duration: 0.8s;"></div>
        <div class="grid-background"></div>
      </div>
      <div
        :class="{
          'background-closed': backgroundClosed,
          'background-open': backgroundOpen
        }"
        class="col"
      >
        <div class="grid-line" style="transition-duration: 0.8s;"></div>
        <div class="grid-background"></div>
      </div>
    </div>
  </div>
</template>

<script>
import { setTimeout } from "timers";
import Header from "./Header.vue";
import MainPage from "./MainPage";
export default {
  name: "animation",
  data() {
    return {
      backgroundClosed: false,
      backgroundOpen: false,
      hidden: false,
      zIndex: 5,
      isShow: true
    };
  },
  components: {
    Header,
    MainPage
  },
  mounted() {
    const self = this;
    this.$nextTick(function() {
      setTimeout(function() {
        self.backgroundClosed = false;
        self.backgroundOpen = true;
      }, 1000);

      setTimeout(function() {
        self.isShow = false;
        self.hidden = true;
        self.backgroundClosed = true;
        self.backgroundOpen = false;
      }, 2000);

      setTimeout(function() {
        self.zIndex = -5;
      }, 2500);
    });
  }
};
</script>

<style lang="scss">
.bg {
  height: 500px;
}

#grid .col {
  float: left;
  box-sizing: border-box;
}

.min-width {
  min-width: 320px;
}
.faded {
  height: 100%;
}
.hidden {
  display: none;
}
.main-background {
  width: 100%;
  z-index: 1;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
}
#grid {
  position: fixed;
  height: 100%;
  left: 343px;
  right: 0;
  z-index: 5;
  display: flex;
}

#menu-background #menu-background-image {
  width: 100%;
  height: 100%;
  // background-image: url(http://tbilisigardens.ge/img/svg-icons/logo-icon.svg);
  background-repeat: no-repeat;
  background-position: center 90%;
  background-size: cover;
  top: 0;
  left: -1.5%;
  z-index: 10;
  transition: opacity 0.2s ease;
}

#menu-background #menu-background-image-new {
  width: 100%;
  height: 100%;
  // background-image: url(https://avatars.mds.yandex.net/get-pdb/199965/1ef8e4ee-9536-4863-9702-4b8667e0a814/s800);
  background-repeat: no-repeat;
  background-position: center 90%;
  background-size: cover;
  top: 0;
  left: -1.5%;
  z-index: 10;
  transition: opacity 0.2s ease;
}

#grid .col {
  position: relative;
  width: 360px;
  height: 100%;
  overflow: hidden;
  box-sizing: content-box;
}

#grid .col .grid-line {
  // border-right: 1px solid rgba(162, 140, 109, 0.2);
  z-index: 10;
  transition: height 0.5s ease;
}

#grid .col .grid-line,
#grid .col .grid-background {
  content: "";
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  box-sizing: border-box;
}

#grid .col.background-open .grid-background {
  -webkit-transform: translateX(0%);
  transform: translateX(0%);
  transition: opacity 0.8s ease 0.15s, -webkit-transform 0.6s ease 0s;
  transition: transform 0.6s ease 0s, opacity 0.8s ease 0.15s;
  transition: transform 0.6s ease 0s, opacity 0.8s ease 0.15s,
    -webkit-transform 0.6s ease 0s;
}

#grid .col .grid-background {
  background-color: white;
  z-index: 5;
  -webkit-transform: translateX(-110%);
  transform: translateX(-110%);
  width: 101%;
}

#grid .col .grid-line,
#grid .col .grid-background {
  content: "";
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  box-sizing: border-box;
}

#grid .col.background-closed .grid-background {
  -webkit-transform: translateX(110%);
  transform: translateX(110%);
  transition: -webkit-transform 0.6s ease 0s;
  transition: transform 0.6s ease 0s;
  transition: transform 0.6s ease 0s, -webkit-transform 0.6s ease 0s;
}
</style>
