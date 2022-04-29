<template>
  <div class="okb-home-section">
    <div class="okb-titlesection">
      <div class="okb-titlecontainer">
        <div class="okb-okay">
          <div v-for="letter in word" class="okb-letter" :class="`okb-letter-${letter}`">
            <img :src="`/img/OKB-${letter.toUpperCase()}.png`" class="okb-image" :class="`okb-image-${letter}`" loading="lazy" alt="">
            <img :src="`/img/OKB-${letter.toUpperCase()}.svg`" class="okb-image-hover" :class="`okb-image-${letter}-hover`" loading="lazy" alt="">
          </div>
          <img src="/img/TitleSection-Bears.svg" loading="lazy" alt="" class="okb-title-section-bears">
        </div>
        <div class="okb-hover-titles">
          <div class="annie-are-you" style="display: none;">Annie are you</div>
          <div class="everything-s-going-to-be" style="display: none;">Everything’s going to be</div>
          <div class="weird-flex-but" style="display: none;">Weird flex but</div>
          <div class="bear-markets-are" style="display: none;">Bear markets are</div>
          <div class="emptytextblock">This is some text inside of a div block.</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      word: "okay"
    }
  }
}
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
    }

    .okb-image-hover:hover {
      opacity: 0;
    }
  }

  .okb-title-section-bears {
    height: 50%;
    position: absolute;
    bottom: 0;
    right: 0;
  }
}

</style>