<template>
  <li @click="handleDisplayName">
    {{ name }}
  </li>
</template>

<script>
export default {
  props: ["name"],
  data() {
    return {
      selected: false,
    };
  },
  methods: {
    handleDisplayName() {
      this.$emit("display-name", this.name);
      this.selected = true;
    },
  },
  // computed: {
  //   selectedMenu() {
  //     return { active: this.selected };
  //   },
  // },
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
