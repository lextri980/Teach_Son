<template>
  <div class="table-container">
    <!-- <b-table striped hover :items="todoList"></b-table> -->
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>Description</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in todoList" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.description }}</td>
          <td>
            <b-button variant="danger" @click="$emit('deleteItem', item.id)"
              >Delete</b-button
            >
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { BButton } from "bootstrap-vue";

export default {
  name: "Table-container",
  props: {
    todoList: {
      type: Array,
    },
  },
  components: {
    // BTable,
    BButton,
  },
  data() {
    return {};
  },
  mounted() {
    console.log(this.todoList);
  },
  methods: {},
};
</script>

<style lang='scss' scoped>
table,
td,
tr,
th {
  border: 1px solid black;
}

td,
th {
  padding: 5px 15px;
}
</style>