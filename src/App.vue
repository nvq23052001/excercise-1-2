<template>
  <menu-list :listMenu="listMenu"></menu-list>
</template>

<script>
import MenuList from "./components/MenuList.vue";

export default {
  components: {
    MenuList,
  },
  data() {
    return {
      listMenu: [
        { id: 1, name: "Home" },
        { id: 2, name: "Services" },
        { id: 3, name: "About" },
        { id: 4, name: "Contact Us" },
      ],
      students: [
        { id: 1, name: "Nguyen Van Quyet" },
        { id: 2, name: "Tran Van Bo" },
        { id: 3, name: "Le Van Tai" },
        { id: 4, name: "Dang Trong Huy" },
      ],
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
  font-size: 62.5%;
}
</style>
