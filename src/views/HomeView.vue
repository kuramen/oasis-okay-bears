<template lang="pug">
Header
.okb-home-section
  .okb-titlesection
    .okb-titlecontainer
      .okb-okay
        .okb-letter(v-for="letter in word" :class="`okb-letter-${letter}`")
          img.okb-image(
            :src="`/img/OKB-${letter.toUpperCase()}.png`"
            :class="`okb-image-${letter}`"
            loading="lazy"
            :alt="`okb-image-${letter}`"
          )
          img.okb-image-hover(
            :src="`/img/OKB-${letter.toUpperCase()}.svg`"
            :class="`okb-image-${letter}-hover`"
            @mouseover="hover = letter"
            @mouseleave="hover = ''"
            loading="lazy"
            :alt="`okb-image-${letter}-hover`"
          )
        img.okb-title-section-bears(src="/img/TitleSection-Bears.svg" loading="lazy" alt="okb-title-section-bears")
      .okb-hover-titles
        .okb-hover-title(
          v-for="letter in word"
          :class="`okb-hover-title-${letter}`"
          v-show="hover === letter"
        ) {{ titles[letter] }}
</template>

<script>
import Header from "@/components/Header.vue";

export default {
  components: { Header },
  data() {
    return {
      word: "okay",
      titles: {
        o: "Annie are you",
        k: "Everything’s going to be",
        a: "Weird flex but",
        y: "Bear markets are",
      },
      hover: "",
    };
  },
};
</script>

<style lang="scss">
.okb-home-section {
  position: absolute;
  display: flex;
  height: 100vh;
  max-width: 100%;
  padding: 0rem 0px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex: 1;
}

.okb-titlesection {
  position: static;
  display: flex;
  height: 800px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex: 1;
  grid-auto-columns: 1fr;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;
}

.okb-titlecontainer {
  display: flex;
  width: 100vw;
  height: 100%;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.okb-okay {
  width: 860px;
  height: 480px;
  position: absolute;
  display: flex;
  max-width: 100%;
  justify-content: center;
  align-items: stretch;

  .okb-letter {
    position: relative;

    .okb-image {
      height: 100%;
      max-width: none;
    }

    .okb-image-hover {
      position: absolute;
      top: 0;
      left: 0;
    }

    .okb-image-k,
    .okb-image-k-hover {
      margin-left: -20px;
    }

    .okb-image-a,
    .okb-image-a-hover {
      margin-left: -90px;
    }

    .okb-image-y,
    .okb-image-y-hover {
      margin-left: 20px;
    }

    .okb-image-hover {
      height: 100%;
      max-width: none;
      opacity: 1;
      mix-blend-mode: multiply;

      &:hover {
        opacity: 0;
      }
    }
  }

  .okb-title-section-bears {
    height: 50%;
    position: absolute;
    bottom: 0;
    right: 0;
  }
}

.okb-hover-titles {
  position: relative;
  top: -32vh;
  left: auto;
  top: -34vh;
  right: auto;
  bottom: auto;
  display: flex;
  width: 80%;
  min-height: 50px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  grid-auto-columns: 1fr;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;

  .okb-hover-title {
    position: absolute;
    color: #bb9772;
  }
}

@media screen and (min-width: 1920px) {
  .okb-titlesection {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
  }

  .okb-hover-titles {
    top: -32vh;
  }

  .okb-titlecontainer {
    flex-direction: column;
    justify-content: center;
  }
}

@media screen and (max-width: 991px) {
  .okb-okay {
    max-height: 70vh;
    height: auto;
    padding: 0;

    .okb-image-hover,
    .okb-image-a,
    .okb-image-y,
    .okb-title-section-bears {
      display: none;
    }

    .okb-letter {
      .okb-image-o,
      .okb-image-k {
        height: 100%;
        width: 100%;
      }

      .okb-image-k {
        margin-left: 0;
      }
    }
  }
}
</style>
