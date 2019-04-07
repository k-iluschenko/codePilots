<template>
  <div class="main__header">
    <div class="header__logo">
      <img src="../assets/img/logo.png" alt="Логотип" />
    </div>
    <div class="header__menu">
      <a
        href="#"
        class="menu__item"
        v-for="(item, index) in menu"
        :key="index"
        >{{ item }}</a
      >
    </div>
    <div class="header__request">
      <c-button :title="'заявка на инвестиции'" :type="'blue'" />
      <c-button :title="'вход'" :className="'button__gray'" :type="'gray'" />
    </div>
  </div>
</template>

<script>
import CButton from "./elements/CButton";
export default {
  name: "Header",
  data() {
    return {
      menu: [
        "главная",
        "о нас",
        "как получить инвестиции",
        "инвесторам",
        "статус проектов",
        "контакты"
      ]
    };
  },
  components: {
    CButton
  }
};
</script>

<style lang="scss">
$color-blue: #0c81fd;
$color-font-dark: #222222;

.main__header {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  padding-left: 24px;
  padding-right: 24px;
  margin-bottom: 200px;
}
.header__logo {
  padding-top: 29px;
  min-width: 320px;
  text-align: left;
}

.header__menu {
  display: flex;
  font-family: "FavoritCondC";
  font-size: 28px;
  text-transform: uppercase;
  color: $color-font-dark;
  & .menu__item {
    display: block;
    text-align: left;
    width: 360px;
    padding-top: 56px;
    position: relative;
    &:before {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      display: block;
      content: "";
      height: 15px;
    }
    &:hover {
      &:before {
        background-color: $color-font-dark;
      }
    }
  }
}

.header__request {
  min-width: 320px;
  display: flex;
  flex-direction: column;
  padding-top: 29px;
  & :nth-child(n) {
    margin-bottom: 17px;
  }
  & :last-child {
    margin-bottom: 0;
  }
}

.button__gray {
  width: 140px;
}
</style>
