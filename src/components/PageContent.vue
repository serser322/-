<template>
  <section class="content grid justify-center sm:grid-cols-3">
    <BaseCard
      v-for="item in introData"
      :key="item.caption"
      :cardData="item"
    />
  </section>
</template>

<script>
import BaseCard from "./BaseCard.vue";
export default {
  name: "PageContent",
  components: {
    BaseCard,
  },
  setup() {
    const introData = [
      {
        caption: "外觀",
        description:
          "白頭鵯體長約17到22公分，額至頭頂純黑色而富有光澤，兩眼上方至後枕白色，形成一白色枕環。耳羽後部有一白斑，此白環與白斑在黑色的頭部均極為醒目，老鳥的枕羽(後頭部)更潔白，所以又叫「白頭翁」。",
      },
      {
        caption: "棲地",
        description:
          "白頭翁和麻雀、綠繡眼合稱「城市三寶」，常成群出現在平原區灌木叢、丘陵樹林地帶，以及校園、公園、庭院、行道中的各種高高的電線與樹上。",
      },
      {
        caption: "食性",
        description:
          "以果樹的漿果和種子為主食，並時常飛入果園偷吃果實，還會吃嫩葉嫩芽，尤其是胡蝶蘭的嫩葉嫩芽葉，偶爾啄食昆蟲。",
      },
    ];

    return {
      introData,
    };
  },
};
</script>

<style lang="scss" scoped>
.content {
  width: auto;
  background-color: #DCCCBC;
  padding: 50.86px 0 71.91px 0;
  gap: 50.5px;
}

@media (min-width: 640px) {
  .content {
    padding: 58.15px 50.74px 84px 50.74px;
    gap: 79px;
  }
}
</style>
