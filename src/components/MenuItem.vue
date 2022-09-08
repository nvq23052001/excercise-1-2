<template>
  <li @click="handleDisplayName" :class="handleActive">
    {{ name }}
  </li>
</template>

<script>
export default {
  props: ["name", "id", "selected"],

  methods: {
    handleDisplayName() {
      this.$emit("display-name", this.name);
    },
  },
  computed: {
    handleActive() {
      return this.id === this.selected ? "active" : "";
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
  background-color: #eeeeee;
  color: #7c8585;
  padding: 15px 25px;
  font-weight: 500;
  font-size: 2.2rem;
  cursor: pointer;
}

li:hover,
li.active {
  background-color: #49c7c2;
  color: #fff;
}
</style>
