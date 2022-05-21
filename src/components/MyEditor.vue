<template>
  <VueEditor :editor="editor" />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { Editor, rootCtx, defaultValueCtx } from '@milkdown/core';
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
import { menu } from '@milkdown/plugin-menu';

export default defineComponent({
  name: 'MilkDown',
  components: {
    VueEditor,
  },
  setup: () => {
    const editor = useEditor((root) =>
      Editor.make()
        .config((ctx) => {
          ctx.set(rootCtx, root);
          ctx.set(defaultValueCtx, '# Milkdown 💖 Vue');
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
    );
    return {
      editor,
    };
  },
});
</script>
<style></style>
