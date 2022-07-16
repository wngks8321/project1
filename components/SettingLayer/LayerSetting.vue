<template>
  <div class="layer_setting">
    <dl>
      <dt>font-family</dt>
      <dd>
        <input ref="fontFamily" type="text" :placeholder="fontSetting.fontFamily">
      </dd>
    </dl>
    <dl>
      <dt>폰트 크기</dt>
      <dd>
        <input ref="fontSize" type="number" :placeholder="fontSetting.fontSize"/>
      </dd>
    </dl>
    <dl>
      <dt>자간</dt>
      <dd>
        <input ref="letterSpacing" type="number" :placeholder="fontSetting.letterSpacing"/>
      </dd>
    </dl>
    <dl>
      <dt>행간</dt>
      <dd>
        <input ref="lineHeight" type="number" :placeholder="fontSetting.lineHeight"/>
      </dd>
    </dl>
    <dl>
      <dt>폰트 굵기</dt>
      <dd>
        <input ref="fontWeight" type="number" :placeholder="fontSetting.fontWeight"/>
      </dd>
    </dl>
    <dl>
      <dt>정렬</dt>
      <dd>
        <select id="" name="" ref="textAlign">
          <option value="left">left</option>
          <option value="center">center</option>
          <option value="right">right</option>
        </select>
      </dd>
    </dl>
    <div class="wrap_button">
      <button 
        type="button" 
        class="btn_submit"
        @click="handleSubmitClick"
      >적용</button>
      <button type="button" class="btn_cancel">취소</button>
    </div>
  </div>
</template>

<script>
/*
  TODO 
    - data의 fontSetting을 defaultStyle 등으로 바꾸고 해당 값으로 template에서 default값 설정

    적용 버튼 클릭 시, 새로운 fontSetting 객체에 this.$refs들의 value를 적용하고, eventBus로 $emit
*/
export default {
  data() {
    return {
      fontSetting: {
        fontFamily: 'https://fonts.googleapis.com/css?family=Noto+Sans+KR',
        fontSize: 14,
        letterSpacing: 1,
        lineHeight: 1.5,
        fontWeight: 400,
        textAlign: 'center',
      }
    }
  },
  mounted() {
  },
  methods: {
    setFontSetting() {
      this.fontSetting.fontFamily = this.$refs.fontFamily.value;
      this.fontSetting.fontSize = this.$refs.fontSize.value;
      this.fontSetting.letterSpacing = this.$refs.letterSpacing.value;
      this.fontSetting.lineHeight = this.$refs.lineHeight.value;
      this.fontSetting.fontWeight = this.$refs.fontWeight.value;
    },
    handleSubmitClick() {
      this.setFontSetting();
    
      this.$bus.$emit('settingSubmit', this.fontSetting);
    }
  }
}
</script>

<style lang="scss" scoped>
  .layer_setting {
    position: absolute;
    padding: 10px;
    bottom: 70px;
    right: 10px;
    background: #999;
  }

  dl {
    display: flex;

    dt {
      width: 100px;
    }
  }

  .wrap_button {
    margin-top: 10px;
    text-align: center;
  }
</style>