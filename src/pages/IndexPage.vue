<template>
  <q-page class="row items-center justify-evenly">
    <div class="inner">
      <MyEditor />
    </div>
  </q-page>
</template>

<script setup lang="ts">
import MyEditor from 'components/MyEditor.vue';
</script>
<style lang="scss">
.inner {
  width: 100%;
  height: 100%;
  overflow: auto;
  z-index: 0;
  position: absolute;
}
.editor {
  height: 100%;
  width: 100%;
}
</style>
