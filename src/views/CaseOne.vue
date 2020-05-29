<template>
  <div class="home">
    <TreeFolder :folder="folder" />
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {
    TreeFolder: () => import("../components/CaseOne/TreeFolder")
  },
  data() {
    return {
      folder: {
        name: "Eh heh",
        children: [
          {
            name: "Eh heh 2",
            children: [
              {
                name: "Eh heh 3"
              },
              {
                name: "Eh heh 6"
              },
              {
                name: "Eh heh 7"
              }
            ]
          },
          //
          {
            name: "Eh heh 4",
            children: [
              {
                name: "Eh heh 5"
              }
            ]
          }
        ]
      }
    };
  }
};
</script>
