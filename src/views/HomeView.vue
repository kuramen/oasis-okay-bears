<template lang="pug">
Header
.oob-home-section
  .oob-titlesection
    .oob-titlecontainer
      .oob-okay
        .oob-letter(v-for="letter in word" :class="`oob-letter-${letter}`")
          img.oob-image(
            :src="`/img/OOB-${letter.toUpperCase()}.png`"
            :class="`oob-image-${letter}`"
            loading="lazy"
            :alt="`oob-image-${letter}`"
          )
          img.oob-image-hover(
            :src="`/img/OOB-${letter.toUpperCase()}.svg`"
            :class="`oob-image-${letter}-hover`"
            @mouseover="hover = letter"
            @mouseleave="hover = ''"
            loading="lazy"
            :alt="`oob-image-${letter}-hover`"
          )
        img.oob-title-section-bears(src="/img/TitleSection-Bears.svg" loading="lazy" alt="oob-title-section-bears")
      .oob-hover-titles
        .oob-hover-title(
          v-for="letter in word"
          :class="`oob-hover-title-${letter}`"
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
.oob-home-section {
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

.oob-titlesection {
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

.oob-titlecontainer {
  display: flex;
  width: 100vw;
  height: 100%;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.oob-okay {
  width: 860px;
  height: 480px;
  position: absolute;
  display: flex;
  max-width: 100%;
  justify-content: center;
  align-items: stretch;

  .oob-letter {
    position: relative;

    .oob-image {
      height: 100%;
      max-width: none;
    }

    .oob-image-hover {
      position: absolute;
      top: 0;
      left: 0;
    }

    .oob-image-k,
    .oob-image-k-hover {
      margin-left: -20px;
    }

    .oob-image-a,
    .oob-image-a-hover {
      margin-left: -90px;
    }

    .oob-image-y,
    .oob-image-y-hover {
      margin-left: 20px;
    }

    .oob-image-hover {
      height: 100%;
      max-width: none;
      opacity: 1;
      mix-blend-mode: multiply;

      &:hover {
        opacity: 0;
      }
    }
  }

  .oob-title-section-bears {
    height: 50%;
    position: absolute;
    bottom: 0;
    right: 0;
  }
}

.oob-hover-titles {
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

  .oob-hover-title {
    position: absolute;
    color: #bb9772;
  }
}

@media screen and (min-width: 1920px) {
  .oob-titlesection {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
  }

  .oob-hover-titles {
    top: -32vh;
  }

  .oob-titlecontainer {
    flex-direction: column;
    justify-content: center;
  }
}

@media screen and (max-width: 991px) {
  .oob-okay {
    max-height: 70vh;
    height: auto;
    padding: 0;

    @media (orientation: landscape) {
      height: 90%;
    }

    .oob-image-hover,
    .oob-image-a,
    .oob-image-y,
    .oob-title-section-bears {
      display: none;
    }

    .oob-letter {
      .oob-image-o,
      .oob-image-k {
        height: 100%;
        width: 100%;
      }

      .oob-image-k {
        margin-left: 0;
      }
    }
  }
}
</style>
