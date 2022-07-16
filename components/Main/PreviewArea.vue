<template>
  <div class="wrap_preview">
    <h2 class="tit_preview">미리보기</h2>
    <div class="wrap_contents">
      <div class="target_preview" :style="computedFontSetting">
        <p v-html="inputData"></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputData: '',
      fontSetting: {}
    }
  },
  created() {
    this.$bus.$on('textAreaKeyup', (data) => {
      const result = data.replaceAll('\n', '<br />');
      this.inputData = result;
    });
  },
  mounted() {
    this.$bus.$on('settingSubmit', (data) => {
      this.fontSetting = data;
    });
  },
  computed: {
    computedFontSetting() {
      return {
        "--font-family": this.fontSetting.fontFamily,
        "--font-size": `${this.fontSetting.fontSize}px`,
        "--letter-spacing": this.fontSetting.letterSpacing,
        "--line-height": this.fontSetting.lineHeight,
        "--font-weight": this.fontSetting.fontWeight,
        "--text-align": this.fontSetting.textAlign,
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrap_preview {
    padding: 10px;
  }

  .tit_preview {
    font-size: 20px;
    text-align: center;
  }

  .wrap_contents {
    margin-top: 10px;
  }

  .target_preview {
    width: 100%;
    min-height: 500px;
    background: powderblue;

    p {
      font-family: var(--font-family);
      font-size: var(--font-size);
      letter-spacing: var(--letter-spacing);
      line-height: var(--letter-spacing);
      font-weight: var(--font-weight);
      text-align: var(--text-align);
    }
  }
</style>