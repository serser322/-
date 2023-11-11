<template>
  <nav class="nav_bar">
    <!-- Mobile screen | Start -->
    <div
      class="nav_bar-mobile sm:hidden"
      :class="{ openedMenu: isMenuOpen }"
    >
      <div class="menu_header grid grid-cols-4 content-center">
        <div
          class="toggler flex items-center"
          @click="toggle"
        >
          <img
            v-if="!isMenuOpen"
            class="w-6 cursor-pointer"
            src="../assets/hamburgur_icon.png"
            alt=""
          />
          <img
            v-if="isMenuOpen"
            class="w-6 cursor-pointer"
            src="../assets/close_icon.png"
            alt=""
          />
        </div>
        <div class="title flex items-center justify-center col-span-2 text-xl font-bold">
          白頭翁不吃小米
        </div>
        <div class="logo flex justify-self-end"></div>
      </div>
      <div
        v-if="isMenuOpen"
        class="menu_options flex justify-center"
      >
        <ol class="grid content-between text-lg">
          <li
            class="cursor-pointer hover:underline hover:font-bold"
            v-for="option in options"
            :key="option"
          >
            <sapn>{{ option }}</sapn>
          </li>
        </ol>
      </div>
    </div>
    <!-- Mobile screen | End -->

    <!-- Desktop screen | Start -->
    <div class="nav_bar-desktop hidden sm:block">
      <div class="menu">
        <div class="title flex justify-center text-3xl font-bold">
          白頭翁不吃小米
        </div>
        <div class="logo"></div>
        <div class="menu_options flex justify-center">
          <ol class="grid text-lg">
            <li
              class="cursor-pointer hover:underline hover:font-bold"
              v-for="option in options"
              :key="option"
            >
              <sapn>{{ option }}</sapn>
            </li>
          </ol>
        </div>
      </div>
    </div>
    <!-- Desktop screen | End-->
  </nav>
</template>

<script>
import { ref } from "vue";
export default {
  name: "NavBar",
  setup() {
    const isMenuOpen = ref(false);
    const options = [
      "白頭翁的特性",
      "白頭翁的故事",
      "白頭翁的美照",
      "白頭翁的危機",
    ];
    const toggle = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };
    return {
      isMenuOpen,
      options,
      toggle,
    };
  },
};
</script>

<style scoped lang="scss">
.nav_bar {

  .nav_bar-mobile {
    .menu_header {
      height: 87.74px;
    }

    .toggler {
      margin-left: 26.38px;
    }

    .title {}

    .logo {
      border: 0.5px solid orange;
      width: 48px;
      height: 48px;
      margin-right: 18.84px;
    }

    .menu_options {
      margin-top: calc(92px - 87.74px);
    }

    .menu_options ol {
      margin-top: calc(92px - 87.74px);
      height: 149.21px;
      text-underline-offset: 4.21px;

      li {
        text-decoration-color: #AA6666;

        :hover {
          color: #AA6666;
        }
      }
    }

    &.openedMenu {
      height: 286.43px;
    }
  }

}

@media (min-width: 640px) {
  .nav_bar {
    .nav_bar-desktop {
      .menu {
        width: 345px;
        height: 100vh;
        position: relative;
        display: inline-block;

        .logo {
          border: 0.5px solid orange;
          width: 97.56px;
          height: 97.04px;
          position: absolute;
          top: 47.31px;
          right: calc(-97.56px/2);
        }

        .title {
          margin-top: 78.33px;
        }

        .menu_options {
          margin-top: 75.67px;

          ol {
            gap: 21.74px;
            text-underline-offset: 4.21px;

            li {
              text-decoration-color: #AA6666;

              :hover {
                color: #AA6666;
              }
            }
          }
        }
      }
    }

  }
}
</style>