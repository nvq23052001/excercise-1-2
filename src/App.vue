<template>
  <menu-list :listMenu="listMenu"></menu-list>
  <search-student :students="students"></search-student>
</template>

<script>
import MenuList from "./components/MenuList.vue";
import SearchStudent from "./components/students/SearchStudent.vue";

export default {
  components: {
    MenuList,
    SearchStudent,
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
        { id: 1, name: "Nguyen Van Quyet", class: "DT50" },
        { id: 2, name: "Tran Van Bo", class: "CK18" },
        { id: 3, name: "Le Van Tai", class: "KD35" },
        { id: 4, name: "Dang Trong Huy", class: "DT50" },
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
