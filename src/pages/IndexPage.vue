<template>
  <q-page class="row items-center justify-evenly">
    <div class="whole-page">
      <MyEditor />
    </div>
  </q-page>
</template>

<script setup lang="ts">
import MyEditor from 'components/MyEditor.vue';
// import { ref } from 'vue';
</script>
<style lang="scss">
.whole-page {
  width: 100%;
  height: 100%;
}
</style>
