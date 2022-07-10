<template>
  <div class="wrap_main">
    <WritingArea class="area_writing" />
    <PreviewArea class="area_preview" />
  </div>
</template>

<script>
import WritingArea from 'components/Main/WritingArea';
import PreviewArea from 'components/Main/PreviewArea';

export default {
  components: {
    WritingArea, 
    PreviewArea
  }
}
</script>

<style lang="scss" scoped>
.wrap_main {
  display: flex;
  justify-content: space-between;

  & > [class*="area_"] {
    flex-basis: 50%;
    height: 100%;
    border: 1px solid #111;
  }
}
</style>