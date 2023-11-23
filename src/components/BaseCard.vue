<template>
  <div class="card flex">
    <div class="caption font-bold text-4xl leading-10">
      {{ cardData.caption }}
    </div>
    <div class="description">
      {{ cardData.description }}
    </div>
  </div>
</template>

<script>
export default {
  name: "BaseCard",
  props: {
    cardData: {
      type: Object,
      default: () => { },
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  margin: 0 36.38px;
  position: relative;
  animation: cardFadeIn 1s ease;

  .caption {
    margin-right: 37.84px;
    width: 36px;
    position: relative;

    &:after {
      content: "";
      display: block;
      position: absolute;
      top: 65.58px;
      left: 27.94px;
      width: 25px;
      height: 25px;
      border-radius: 50%;
      border: 8px solid rgba(170, 102, 102, 60%);
    }
  }
}

@keyframes cardFadeIn {
  0% {
    opacity: 0;
    bottom: -50px;
  }

  50% {
    opacity: 0;
    bottom: -50px;
  }

  100% {
    opacity: 100%;
    bottom: 0px;
  }
}

@media (min-width: 768px) {
  .card {
    margin: 0;
  }
}
</style>