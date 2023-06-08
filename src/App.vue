<template>
  <div id="app">
    <ChangeTab />
    <Table :todoList="todoList" @deleteItem="deleteItem"></Table>
  </div>
</template>

<script>
import ChangeTab from "./page/changeTab.vue";
import Table from "./components/Table.vue";

export default {
  name: "App",
  components: { ChangeTab, Table },
  data() {
    return {
      product: "",
      product1Way: "",
      products: [
        { id: 1, name: "milk" },
        { id: 2, name: "rice" },
        { id: 3, name: "laptop" },
        { id: 4, name: "fruit" },
        { id: 5, name: "beverage" },
      ],
      message: "Count message",
      count: 3,
      isShow: true,
      inputType: "text",
      width: 1,
      height: 2,
      some: {
        nested: {
          key: 0,
        },
      },
      todoList: [
        { id: 1, name: "Take an SAD exam", description: "2 days" },
        { id: 2, name: "Take an MLA exam", description: "2 days" },
        { id: 3, name: "Take an DSA exam", description: "3 days" },
        { id: 4, name: "Take an CAL exam", description: "4 days" },
        { id: 5, name: "Take an NSE exam", description: "4 days" },
        { id: 6, name: "Take an DBS exam", description: "4 days" },
        { id: 7, name: "Take an DBA exam", description: "6 days" },
        { id: 8, name: "Take an BDM exam", description: "7 days" },
      ],
    };
  },
  beforeCreate() {},
  created() {},
  beforeMount() {},
  mounted() {
    this.calling();
  },
  beforeDestroy() {},
  destroyed() {},
  computed: {
    perimeter: {
      get() {
        let pOfRectangle;
        if (!this.width) {
          pOfRectangle = (1 + this.height) * 2;
        } else if (!this.height) {
          pOfRectangle = (1 + this.width) * 2;
        } else {
          pOfRectangle = (this.height + this.width) * 2;
        }
        return pOfRectangle;
      },
    },
  },
  watch: {
    "some.nested.key"() {
      this.calling();
    },
  },
  methods: {
    deleteItem(id) {
      this.todoList = this.todoList.filter((item) => {
        return item.id !== id;
      });
    },
    upNumber() {
      this.some.nested.key += 1;
    },

    calling() {
      // console.log("change recalled " + this.some.nested.key);
    },
    called() {
      return 3;
    },
    showPassword() {
      this.isShow = !this.isShow;
    },
    countUp() {
      return this.count + 2;
    },
    showInput() {
      if (this.inputType === "text") {
        this.inputType = "datetime";
      } else {
        this.inputType = "text";
      }
    },
  },
};
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
}

.show {
  display: block;
}

.hidden {
  display: none;
}
</style>
