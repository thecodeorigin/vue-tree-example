<template>
  <div class="two">
    <div id="tree">
      <Item
        v-for="item in temp"
        :key="item.name"
        :content="item.name"
        :margin="item.margin"
      />
    </div>
  </div>
</template>
<script>
export default {
  components: {
    Item: () => import("../components/CaseTwo/Item")
  },
  data() {
    return {
      folder: [
        {
          id: 1,
          name: "Hello",
          parentId: null
        },
        {
          id: 2,
          name: "Hello 2",
          parentId: null
        },
        {
          id: 3,
          name: "Hello 3",
          parentId: 1
        },
        {
          id: 4,
          name: "Hello 4",
          parentId: 2
        },
        {
          id: 5,
          name: "Hello 5",
          parentId: 3
        },
        {
          id: 6,
          name: "Hello 9",
          parentId: 3
        }
      ],
      temp: []
    };
  },
  methods: {
    createTree(array, pivot, margin = 0) {
      array.forEach(item => {
        if (item.parentId == pivot) {
          // console.log(str + item.name);
          // console.log(this.$el.querySelector("#tree"));
          item.margin = margin;
          this.temp.push(item);
          this.createTree(array, item.id, margin + 20);
        }
      });
    }
  },
  async mounted() {
    await this.createTree(this.folder, null);
  }
};
</script>
