<template>
  <nav class="nav_bar">
    <!-- Mobile screen | Start -->
    <div
      class="nav_bar-mobile md:hidden"
      :class="{ openedMenu: isMenuOpen }"
    >
      <div class="menu_header grid grid-cols-4 content-center">
        <div
          class="toggler flex items-center"
          @click="toggle"
        >
          <img
            class="w-6 cursor-pointer"
            :class="{ showHamburgur: !isMenuOpen, hiddenHamburgur: isMenuOpen }"
            src="../assets/hamburgur_icon.png"
            alt=""
          />
          <img
            class="w-6 cursor-pointer"
            :class="{ showClose: isMenuOpen, hiddenClose: !isMenuOpen }"
            src="../assets/close_icon.png"
            alt=""
          />
        </div>
        <div class="title flex items-center justify-center col-span-2 text-xl font-bold">
          白頭翁不吃小米
        </div>
        <div class="logo justify-self-end">
          <BirdLogo class="web_logo" />
        </div>
      </div>
      <div
        class="menu_options flex justify-center"
        :class="{ show: isMenuOpen }"
      >
        <ol class="grid content-between text-lg">
          <li
            class="cursor-pointer"
            :class="[option.isSelected ? ['selected', 'underline'] : '']"
            v-for="option in options"
            :key="option.optionName"
            @click="selectOption(option.optionName)"
          >
            <span>{{ option.optionName }}</span>
          </li>
        </ol>
      </div>
    </div>
    <!-- Mobile screen | End -->

    <!-- Desktop screen | Start -->
    <div class="nav_bar-desktop hidden md:block">
      <div class="menu">
        <div class="title flex justify-center md:text-xl lg:text-3xl font-bold">
          白頭翁不吃小米
        </div>
        <div class="logo">
          <BirdLogo class="web_logo" />
        </div>
        <div class="menu_options flex justify-center">
          <ol class="grid text-lg">
            <li
              class="cursor-pointer"
              :class="[option.isSelected ? ['selected', 'underline'] : '']"
              v-for="option in options"
              :key="option.optionName"
              @click="selectOption(option.optionName)"
            >
              <span>{{ option.optionName }}</span>
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
import BirdLogo from "./BirdLogo.vue";

export default {
  name: "NavBar",
  components: {
    BirdLogo,
  },
  setup() {
    const isMenuOpen = ref(false);
    const options = ref([
      {
        optionName: "白頭翁的特性",
        isSelected: false,
      },
      {
        optionName: "白頭翁的故事",
        isSelected: false,
      },
      {
        optionName: "白頭翁的美照",
        isSelected: false,
      },
      {
        optionName: "白頭翁的危機",
        isSelected: false,
      },
    ]);
    const toggle = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };
    const selectOption = (optionName) => {
      options.value.forEach((opt) => {
        opt.isSelected = opt.optionName === optionName;
      });
    };
    return {
      isMenuOpen,
      options,
      toggle,
      selectOption,
    };
  },
};
</script>

<style scoped lang="scss">
.nav_bar {
  .nav_bar-mobile {
    height: 87.74px;
    transition: height 0.5s ease;

    &:before {
      content: "";
      display: block;
      width: 100%;
      height: 87.74px;
      position: absolute;
      top: 0;
      left: 0;
      background-color: white;
      z-index: 2;
    }

    .menu_header {
      height: 87.74px;
      position: relative;
      z-index: 3;

      .toggler {
        margin-left: 26.38px;
        position: relative;

        .showHamburgur {
          visibility: block;
          position: absolute;
          opacity: 100%;
          transform: rotate(0deg);
          transition: all 0.5s ease;
        }

        .hiddenHamburgur {
          visibility: hidden;
          position: absolute;
          opacity: 0;
          transform: rotate(180deg);
          transition: all 0.5s ease;
        }

        .showClose {
          visibility: block;
          position: absolute;
          opacity: 100%;
          transform: rotate(0deg);
          transition: all 0.5s ease;
        }

        .hiddenClose {
          visibility: hidden;
          position: absolute;
          opacity: 0;
          transform: rotate(-180deg);
          transition: all 0.5s ease;
        }
      }

      .logo {
        width: 48px;
        height: 48px;
        margin-right: 18.84px;
        border-radius: 50%;
        background-color: white;
        box-shadow: 5px 5px 10px rgba($color: #000000, $alpha: 0.25);
        position: relative;

        .web_logo {
          position: absolute;
          top: 12px;
          left: 13px;
        }
      }
    }

    .menu_options {
      margin-top: calc(92px - 87.74px);
      display: hidden;
      opacity: 0%;
      position: relative;
      top: -240px;
      z-index: 1;
      transition: all 0.5s ease;

      &.show {
        display: flex;
        position: relative;
        opacity: 100%;
        top: 0px;
      }
    }

    .menu_options ol {
      margin-top: calc(92px - 87.74px);
      height: 149.21px;
      text-underline-offset: 4.21px;

      li {
        text-decoration-color: #AA6666;

        :hover {
          color: #AA6666;
          text-decoration: underline;
          font-weight: bold;
        }

        :active {
          color: salmon;
        }

        &.selected {
          color: #AA6666;
        }
      }
    }

    &.openedMenu {
      height: 286.43px;
    }
  }
}

@media (min-width: 768px) {
  .nav_bar {
    .nav_bar-desktop {
      .menu {
        width: 250px;
        height: 100vh;
        position: relative;
        display: inline-block;
        animation: menuFadeIn 1s ease;

        .logo {
          width: 97px;
          height: 97px;
          position: absolute;
          top: 47.31px;
          border-radius: 50%;
          right: calc(-97.56px / 2);
          background-color: white;
          box-shadow: 5px 5px 10px rgba($color: #000000, $alpha: 0.25);
          animation: logoRotate 0.5s ease;

          .web_logo {
            transform: scale(2);
            position: relative;
            top: 35px;
            left: 38px;
          }

          @keyframes logoRotate {
            0% {
              transform: rotate(-180deg);
            }

            100% {
              transform: rotate(0);
            }
          }
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
                text-decoration: underline;
                font-weight: bold;
              }

              :active {
                color: salmon;
              }

              &.selected {
                color: #AA6666;
              }
            }
          }
        }
      }
    }
  }
}

@keyframes menuFadeIn {
  0% {
    opacity: 0;
    left: -30px;
  }

  100% {
    opacity: 100%;
    left: 0;
  }
}

@media (min-width: 1024px) {
  .nav_bar {
    .nav_bar-desktop {
      .menu {
        width: 345px;
      }
    }
  }
}</style>