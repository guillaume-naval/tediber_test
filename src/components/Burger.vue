<template>
  <div class="burger" :class="{ close: isBurgerActive }" @click="toggle()">
    <span class="burger-line line01"></span>
    <span class="burger-line line02"></span>
    <span class="burger-line line03"></span>
  </div>
</template>

<script>
export default {
  name: "Burger",
  props: {
    isBurgerActive: {
      type: Boolean,
      required: true,
      default: false,
    },
  },
  methods: {
    toggle() {
      this.$emit("toggleMenu");
    },
  },
};
</script>
<style scoped lang="scss">
.burger {
  display: flex;
  width: 26px;
  height: 32px;
  position: relative;
  cursor: pointer;

  @media screen and (min-width: 1200px) {
    display: none;
  }
}
.burger-line {
  position: absolute;
  height: 2px;
  width: 100%;
  background: black;
  transition: all cubic-bezier(0.25, 0.1, 0.28, 1.54) 0.32s;
}
.line01 {
  top: 19%;
}
.line02 {
  top: 49%;
}
.line03 {
  top: 79%;
}
.burger.close .line01 {
  transform: rotate(45deg);
  top: 49%;
}
.burger.close .line02,
.burger.close .line03 {
  transform: rotate(-45deg);
  top: 49%;
}
</style>
