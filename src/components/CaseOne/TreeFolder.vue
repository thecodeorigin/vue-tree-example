<template>
  <div>
    <span>{{ folder.name }}</span>
    <tree-folder-contents :children="folder.children" />
  </div>
</template>
<script>
export default {
  props: ["folder"],
  components: {
    TreeFolderContents: () => import("./TreeFolderContents.vue")
  }
};
</script>
