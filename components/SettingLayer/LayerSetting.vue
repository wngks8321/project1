<template>
  <div class="layer_setting">
    <dl>
      <dt>font-family</dt>
      <dd>
        <input type="text" placeholder="https://fonts.googleapis.com/css?family=Noto+Sans+KR">
      </dd>
    </dl>
    <dl>
      <dt>폰트 크기</dt>
      <dd>
        <input type="number" placeholder="12"/>
      </dd>
    </dl>
    <dl>
      <dt>자간</dt>
      <dd>
        <input type="number" placeholder="1"/>
      </dd>
    </dl>
    <dl>
      <dt>행간</dt>
      <dd>
        <input type="number" placeholder="1.5"/>
      </dd>
    </dl>
    <dl>
      <dt>폰트 굵기</dt>
      <dd>
        <input type="number" placeholder="600"/>
      </dd>
    </dl>
    <dl>
      <dt>정렬</dt>
      <dd>
        <select id="" name="">
          <option value="left">left</option>
          <option value="center">center</option>
          <option value="right">right</option>
        </select>
      </dd>
    </dl>
  </div>
</template>

<script>
export default {

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
</style>