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
      <div class="title__img">
        <img src="../assets/img/title.png" alt="title" />
      </div>
    </div>
    <div class="wrapper"></div>
  </div>
</template>

<script>
export default {};
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
      left: 30px;
      z-index: -1;
    }
  }
}

.wrapper {
  min-width: 320px;
  display: flex;
}
</style>
