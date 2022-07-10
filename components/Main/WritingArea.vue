<template>
  <div class="wrap_writing">
    <h2 class="tit_writing">텍스트 입력 란</h2>
    <div class="wrap_contents">
      <textarea 
        id="WritingTextArea"
        class="textarea_writing"
        name="inputText"
        placeholder="이곳에 텍스트를 입력하세요."
        @keyup="handleInput"
      >
      </textarea>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleInput(event) {
      this.$bus.$emit('textAreaKeyup', event.target.value);
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrap_writing {
    padding: 10px;
  }

  .tit_writing {
    font-size: 20px;
    text-align: center;
  }

  .wrap_contents {
    margin-top: 10px;
  }

  .textarea_writing {
    width: 100%;
    min-height: 500px;
    padding: 0;
    box-sizing: border-box;
    resize: none;
  }
</style>