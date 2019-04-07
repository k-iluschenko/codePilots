<template>
  <a :href="url" :class="[type, className, 'button']">{{ title }}</a>
</template>

<script>
export default {
  name: "c-button",
  props: {
    title: String,
    type: String,
    className: String,
    url: String
  }
};
</script>

<style lang="scss">
$color-gray: #ebebeb;
$color-blue: #0c81fd;

.button {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 30px;
  height: 107px;
  font-size: 28px;
  text-transform: uppercase;
}

.gray {
  background: $color-gray;
}
.blue {
  background: $color-blue;
  color: #fff;
}
</style>
