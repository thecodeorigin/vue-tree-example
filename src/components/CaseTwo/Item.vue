<template>
  <div :style="'text-align: left; padding-left: ' + margin + 'px'">
    {{ content }}
  </div>
</template>
<script>
export default {
  props: ["content", "margin"]
};
</script>
