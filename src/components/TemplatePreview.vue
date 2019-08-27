<template>
  <div class="wrapper">
    <div class="one">
      <button class="btn-top">Top</button>
    </div>
    <div class="two">
      <button class="btn-right">Right</button>
    </div>
    <div class="three">
      <button class="btn-bottom">Bottom</button>
    </div>
    <div class="four">
      <button class="btn-left">Left</button>
    </div>
    <div class="bord five"></div>
  </div>
</template>

<script>
export default {
  props: {
    veneerSide: {
      type: Object,
      default: function() {
        return {
          top: false,
          bottom: false,
          left: false,
          right: false
        };
      }
    }
  }
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
    // border: 2px solid rgb(233, 171, 88);
    // border-radius: 5px;
  }

  .bord {
    // border: 2px solid rgb(233, 171, 88);
    // border-radius: 5px;
    background-image: url("../assets/wooden-textured.jpg");
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
</style>