<template>
  <div class="change-tab-container">
    <div class="tab-btn-group">
      <div
        v-for="(item, index) in title"
        class="btn-item"
        :class="item === titleRendered ? 'activate' : ''"
        :key="index"
        @click="handleChangeTab(item, index)"
      >
        {{ item }}
      </div>
    </div>
    <p>{{ titleRendered }}</p>
    <p>{{ contentRendered }}</p>
  </div>
</template>

<script>
export default {
  name: "change-tab",
  data() {
    return {
      title: ["React", "Angular", "Ember", "Vue"],
      content: [
        "React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.",
        "Angular is an application design framework and development platform for creating efficient and sophisticated single-page apps.",
        "Ember.js is a productive, battle-tested JavaScript framework for building modern web applications. It includes everything you need to build rich UIs that work on any device.",
        "Vue (pronounced /vju:/, like view) is a progressive framework for building user interfaces. Unlike other monolithic frameworks, Vue is designed from the ground up to be incrementally adoptable.",
      ],
      contentRendered: "",
      titleRendered: "",
    };
  },
  mounted() {
    this.contentRendered = this.content[0];
    this.titleRendered = this.title[0];
  },
  methods: {
    handleChangeTab(item, index) {
      this.contentRendered = this.content[index];
      this.titleRendered = item;
    },
  },
};
</script>

<style scoped>
.change-tab-container {
  width: calc(100vw - 40px);
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  align-items: flex-start !important;
}
.tab-btn-group {
  display: flex;
  gap: 30px;
}

.btn-item {
  border: 1px solid black;
  padding: 5px 10px;
}

.btn-item:hover {
  cursor: pointer;
}

.activate {
  background-color: black;
  color: white;
}
</style>