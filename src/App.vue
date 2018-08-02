<template>
  <div id="app">
  Drag an image over to the editor content area and drop it in to test this module 
  <vue-editor
    v-model="content"
    :editor-options="editorSettings">
  </vue-editor>
  </div>
</template>

<script>
import { VueEditor, Quill } from 'vue2-editor';
import { ImageDrop } from 'quill-image-drop-module';

Quill.register('modules/imageDrop', ImageDrop);

export default {
  name: 'App',
  components: {
    VueEditor
  },
  data: () => ({
    content: '',
    editorSettings: {
      modules: {
        imageDrop: true
      }
    }
  })
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
