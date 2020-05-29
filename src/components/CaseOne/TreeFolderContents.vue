<template>
  <ul>
    <li v-for="child in children" :key="child.name">
      <tree-folder v-if="child.children" :folder="child" />
      <span v-else>{{ child.name }}</span>
    </li>
  </ul>
</template>
<script>
export default {
  props: ["children"],
  components: {
    TreeFolder: () => import("./TreeFolder.vue")
  }
};
</script>
<style>
ul {
  list-style: none;
  border-left: 1px dashed grey;
  margin: 0.25rem;
}
</style>
