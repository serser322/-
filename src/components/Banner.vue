<template>
  <div class="banner flex flex-col justify-end bg-no-repeat text-white md:items-end">
    <div class="title font-bold flex flex-col self-end lg:flex-row md:justify-end">
      <div class="text-5xl text-right leading-none">白頭翁</div>
      <div class="text-5xl text-right leading-none">(Chinese bulbul)</div>
    </div>
    <div class="introduction text-lg">
      又名白頭鵯。以果實、昆蟲為主食，無法消化小米、穀類。平均壽命約 8~10 年。
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
};
</script>

<style scoped lang="scss">
.banner {
  height: 311px;
  background-image: url(banner.png);
  background-size: 180%;
  background-position: 60%;
  background-repeat: no-repeat;

  .title {
    width: 60%;
    margin: 0 26.95px 9.35px auto;
    position: relative;
    animation: textFadeIn 0.7s ease;
  }

  .introduction {
    margin: 0 22.67px 24.07px 22.67px;
    position: relative;
    animation: textFadeIn 0.7s ease;
  }
}

@keyframes textFadeIn {
  0% {
    opacity: 0;
    right: -50px;
  }

  100% {
    opacity: 100%;
    right: 0px;
  }
}

@media (min-width: 768px) {
  .banner {
    min-height: 450px;
    background-size: 180%;
    background-position: 60%;

    .title {
      width: 100%;
      margin: 0 44.75px 4px 0;
    }

    .introduction {
      margin: 0 44.75px 20px 44.75pxpx;
      /* padding: 0 5px 0 5px;
      margin-bottom: 20px; */
    }
  }
}

@media (min-width: 1024px) {
  .banner {
    min-height: 634.21px;
    background-size: 180%;
    background-position: 70%;
  }

  .introduction {
    margin-bottom: 36.85px;
  }
}
</style>