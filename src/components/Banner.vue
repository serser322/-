<template>
  <div class="banner flex flex-col justify-end bg-no-repeat text-white sm:items-end">
    <div class="title font-bold flex flex-col self-end sm:flex-row sm:justify-end">
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
  }

  .introduction {
    margin: 0 22.67px 24.07px 22.67px;
  }
}

@media (min-width:640px) {
  .banner {
    height: 634.21px;
    background-size: 155%;
    background-position: 80%;

    .title {
      width: 100%;
      margin: 0 44.75px 4px 0;
    }

    .introduction {
      margin: 0;
      margin: 0 44.75px 36.85px 0;
    }
  }
}
</style>