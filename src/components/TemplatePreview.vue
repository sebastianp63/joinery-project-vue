<template>
  <div class="wrapper">
    <div class="one"></div>
    <div class="two"></div>
    <div class="three"></div>
    <div class="four"></div>
    <div
      class="bord five"
      v-bind:class="{ 
      'top-border': topBorder,
      'bottom-border': bottomBorder,
      'left-border': leftBorder,
      'right-border': rightBorder
      }"
    ></div>
  </div>
</template>

<script>
export default {
  props: {
    topBorder: Boolean,
    bottomBorder: Boolean,
    leftBorder: Boolean,
    rightBorder: Boolean
  },
  metods: {}
};
</script>
<style lang="scss" scoped>
* {
  box-sizing: border-box;
}
.wrapper {
  max-width: 940px;
  margin: 0 auto;

  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
  grid-auto-rows: minmax(100px, auto);

  div {
    position: relative;
  }

  .bord {
    //border: 2px solid rgb(233, 171, 88);
    // border-radius: 5px;
    background-color: burlywood;
    // background-image: url("../assets/wooden-textured.jpg");
    // color: #d9480f;
  }
}

.one {
  grid-column: 2 / 4;
  grid-row: 1 / 2;
}
.two {
  grid-column: 4 / 5;
  grid-row: 2 / 4;
}
.three {
  grid-column: 2/4;
  grid-row: 4 / 5;
}
.four {
  grid-column: 1 /2;
  grid-row: 2/ 4;
}
.five {
  grid-column: 2 / 4;
  grid-row: 2 / 4;
}

.vertical-text {
  writing-mode: vertical-rl;
  text-orientation: mixed;
}

.btn-top {
  position: absolute;
  height: 60px;
  bottom: 0;
  left: 0;
  width: 100%;
}

.btn-right {
  position: absolute;
  top: 0;
  left: 0;
  width: 60px;

  height: 100%;
}

.btn-bottom {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 50px;
}

.btn-left {
  position: absolute;
  top: 0;
  right: 0;
  width: 60px;
  height: 100%;
}

.top-border {
  border-top: 5px solid brown;
}

.bottom-border {
  border-bottom: 5px solid brown;
}

.left-border {
  border-left: 5px solid brown;
}

.right-border {
  border-right: 5px solid brown;
}
</style>