<template>
  <div>
    <input type="text" placeholder="Search" @input="handleValueSearch" />
  </div>

  <div>
    <ul>
      <StudentsList :listStudents="listSearchStudents"></StudentsList>
    </ul>
  </div>
</template>

<script setup>
import { ref, defineProps } from "vue";

import StudentsList from "./StudentsList.vue";

const props = defineProps(["students"]);

const enteredSearch = ref("");
const listSearchStudents = ref(props.students);

function handleValueSearch(e) {
  enteredSearch.value = e.target.value;
  listSearchStudents.value = props.students.filter((student) => {
    if (
      student.name.includes(enteredSearch.value) ||
      student.class.includes(enteredSearch.value)
    ) {
      return student;
    }
  });
}
</script>

<style scoped>
div {
  display: flex;
  justify-content: center;
  margin-top: 40px;
}
input {
  width: 510px;
  padding: 5px;
  height: 60px;
  border: 8px solid #a5d8d6;
  font-size: 1.8rem;
  outline: none;
  color: #747777;
}

ul {
  width: 510px;
  padding: 5px;
  height: 60px;
  list-style: none;
}

::placeholder {
  text-align: center;
  font-size: 2rem;
}
</style>
