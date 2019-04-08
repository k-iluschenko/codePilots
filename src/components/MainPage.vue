<template>
  <div class="section__main">
    <div class="phone__wrapper">
      <div class="main__phone">8 (800) 777-77-77</div>
    </div>
    <div class="main__title">
      <div class="title__content">
        <div class="title__header">маи</div>
        <div class="title__text">
          <div>международная ассоциация</div>
          <div>
            <span>инвесторов</span>
          </div>
        </div>
      </div>
      <div v-if="isShow" class="title__img">
        <img src="../assets/img/title.png" alt="title" />
      </div>
      <div v-else class="main__about">
        <div class="about__title">Инвестиции в перспективные проекты.</div>
        <div class="about__title">
          МАИ - крупнейшая инвестиционная организация восточной Европы.
        </div>
        <c-button
          :title="'заявка на инвестиции'"
          :type="'blue'"
          :className="'button__blue'"
        />
        <div class="about__text">
          Расскажите о вашем проекте и подайте заявку на инвестирование
        </div>
      </div>
    </div>
    <div class="wrapper"></div>
  </div>
</template>

<script>
import CButton from "./elements/CButton";
export default {
  name: "MainPage",
  props: {
    isShow: Boolean
  },
  components: {
    CButton
  }
};
</script>

<style lang="scss">
$color-blue: #0c81fd;
$color-dark: #222222;

.section__main {
  font-family: "Cocogoose Compressed Trial Regular";
  display: flex;
}

.phone__wrapper {
  font-family: "FavoritCondC";
  font-size: 28px;
  color: #fff;
  min-width: 343px;
  & .main__phone {
    display: flex;
    justify-content: center;
    align-items: center;
    background: $color-dark;
    height: 106px;
    padding-left: 23px;
    padding-right: 43px;
    margin-right: 70px;
  }
}

.main__title {
  display: flex;
  width: 100%;
  & .title__content {
    text-align: left;
    width: 720px;
    margin-right: 510px;
    & .title__header {
      font-size: 350px;
      line-height: 271px;
      text-transform: uppercase;
      color: $color-blue;
    }
    & .title__text {
      font-size: 80px;
      color: $color-dark;
      & span {
        color: $color-blue;
      }
    }
  }
  & .title__img {
    position: relative;
    width: 100%;
    & img {
      position: absolute;
      top: -215px;
      left: -510px;
      z-index: -1;
    }
  }
}

.main__about {
  text-align: left;
  & .about__title {
    font-family: "Roboto Condensed";
    font-size: 60px;
    margin-bottom: 10px;
  }
  & .about__text {
    font-family: "Roboto Condensed";
    font-size: 28px;
    width: 450px;
  }
}
.button__blue {
  font-family: "FavoritCondC";
  font-size: 28px;
  width: 260px;
  margin-top: 130px;
  margin-bottom: 60px;
}
.wrapper {
  min-width: 320px;
  display: flex;
}
</style>
