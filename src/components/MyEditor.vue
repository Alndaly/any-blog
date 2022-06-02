<template>
  <VueEditor :editor="editor" />
</template>

<script lang="ts" setup>
import { Editor, rootCtx } from '@milkdown/core';
import { nord } from '@milkdown/theme-nord';
import { VueEditor, useEditor } from '@milkdown/vue';
import { emoji } from '@milkdown/plugin-emoji';
import { history } from '@milkdown/plugin-history';
import { listener } from '@milkdown/plugin-listener';
import { prism } from '@milkdown/plugin-prism';
import { math } from '@milkdown/plugin-math';
import { slash } from '@milkdown/plugin-slash';
import { diagram } from '@milkdown/plugin-diagram';
import { upload } from '@milkdown/plugin-upload';
import { gfm } from '@milkdown/preset-gfm';
import { indent } from '@milkdown/plugin-indent';
import { menu } from '@milkdown/plugin-menu';

const editor = useEditor((root) =>
  Editor.make()
    .config((ctx) => {
      ctx.set(rootCtx, root);
    })
    .use(nord)
    .use(emoji)
    .use(gfm)
    .use(history)
    .use(listener)
    .use(menu)
    .use(prism)
    .use(math)
    .use(slash)
    .use(diagram)
    .use(upload)
    .use(indent)
);
</script>
<style lang="scss">
.container {
  position: relative;
  display: block;
  margin: 0 auto;
  transition: all 0.4s ease-in-out;
}
.milkdown-menu {
  position: sticky;
  top: 0;
  z-index: 10000;
}
</style>
