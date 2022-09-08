<template>
  <nav>
    <ul>
      <menu-item
        @display-name="handleDisplay"
        v-for="menu in listMenu"
        :key="menu.id"
        :name="menu.name"
        :id="menu.id"
        @click="handleSelected(menu.id)"
        :selected="selected"
      />
    </ul>
    <h3 v-if="nameItem">Selected: {{ nameItem }}</h3>
  </nav>
</template>

<script>
import MenuItem from "./MenuItem.vue";
export default {
  props: ["listMenu"],
  data() {
    return {
      nameItem: "",
      selected: null,
    };
  },
  components: {
    MenuItem,
  },
  methods: {
    handleDisplay(name) {
      this.nameItem = name;
    },
    handleSelected(id) {
      this.selected = id;
    },
  },
};
</script>

<style scoped>
ul {
  display: flex;
  justify-content: center;
  list-style: none;
}

h3 {
  font-size: 2.5rem;
  color: #747777;
  font-weight: 200;
  text-align: center;
  margin-top: 20px;
}
</style>
>
