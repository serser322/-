<template>
  <div class="web_logo">
    <div class="top"></div>
    <div class="eye"></div>
    <div class="beak">
      <div class="beak-modifing"></div>
    </div>
    <div class="beak-mask"></div>
    <div class="bottom"></div>
  </div>
</template>

<script>
</script>

<style lang="scss" scoped>
.web_logo {
  width: 24px;
  height: 21px;

  .top {
    width: 22px;
    height: 12px;
    position: absolute;
    overflow: hidden;

    &:before {
      content: "";
      width: 22px;
      height: 22px;
      position: absolute;
      background-color: black;
      border-radius: 70% 45% / 65% 50%;
    }

    &:after {
      content: "";
      width: 22px;
      height: 22px;
      position: absolute;
      top: 4px;
      left: 0px;
      background-color: white;
      border-radius: 65% 40%/ 41% 15%;
    }
  }

  .eye {
    width: 5px;
    height: 5px;
    position: absolute;
    top: 7px;
    right: 6px;
    border-radius: 50%;
    background-color: black;
    z-index: 3;
  }

  .beak {
    width: 12px;
    height: 6px;
    position: absolute;
    top: 5px;
    right: -5px;
    overflow: hidden;

    &:before {
      content: "";
      width: 9px;
      height: 10px;
      position: absolute;
      top: 0.5px;
      right: 0;
      background-color: black;
      border-top-right-radius: 65% 60%;
      transform: rotate(-20deg);
    }

    &:after {
      content: "";
      width: 10px;
      height: 10px;
      position: absolute;
      top: 3px;
      right: -2px;
      background-color: white;
      border-top-right-radius: 80% 30%;
      transform: rotate(-30deg);
    }

    .beak-modifing {
      width: 7px;
      height: 10px;
      position: absolute;
      top: -2px;
      right: 9px;
      border-radius: 50%;
      background-color: white;
      transform: rotate(-40deg);
    }
  }

  .beak-mask {
    width: 9px;
    height: 4px;
    position: relative;
    top: 9px;
    left: 21px;
    background-color: white;
    border-radius: 50%;
    transform: rotate(-18deg);
    z-index: 3;
  }

  .bottom {
    width: 23px;
    height: 10px;
    position: absolute;
    bottom: 0px;
    right: 1px;
    overflow: hidden;
    z-index: 1;

    &:before {
      content: "";
      width: 22px;
      height: 8px;
      position: absolute;
      bottom: 0;
      left: 0px;
      background-color: black;
      border: 0.1px solid white;
      border-bottom-right-radius: 50% 95%;
    }

    &:after {
      content: "";
      display: block;
      position: absolute;
      width: 22px;
      height: 8px;
      bottom: 4px;
      left: 0;
      background-color: white;
      border-bottom-right-radius: 50% 55%;
    }
  }
}
</style>