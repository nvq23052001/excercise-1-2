<template>
  <li v-for="student in props.listStudents" :key="student.id">
    <span>{{ student.name }}</span>
    <span>{{ student.class }}</span>
  </li>
</template>
<script setup>
import { defineProps } from "vue";

const props = defineProps(["listStudents"]);
</script>

<style scoped>
li {
  color: #7c8585;
  font-size: 2.8rem;
  background-color: #eeeeee;
  padding: 15px 10px;
  margin-top: 5px;
  display: flex;
}

span {
  margin-right: 40px;
  min-width: 150px;
}
</style>
