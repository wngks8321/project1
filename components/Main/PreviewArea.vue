<template>
  <div class="wrap_preview">
    <h2 class="tit_preview">미리보기</h2>
    <div class="wrap_contents">
      <div class="target_preview">
        <p v-html="inputData"></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputData: ''
    }
  },
  created() {
    this.$bus.$on('textAreaKeyup', (data) => {
      const result = data.replaceAll('\n', '<br />');
      this.inputData = result;
    });
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
  }
</style>