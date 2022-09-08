<template>
  <div>
    <input type="text" placeholder="Search" @input="handleValueSearch" />
  </div>

  <div>
    <ul>
      <students-list :listStudents="listSearchStudents"></students-list>
    </ul>
  </div>
</template>

<script>
import StudentsList from "./StudentsList.vue";
export default {
  components: {
    StudentsList,
  },
  props: ["students"],
  data() {
    return {
      enteredSearch: "",
      listSearchStudents: this.students,
    };
  },
  methods: {
    handleValueSearch(e) {
      console.log("a");
      this.enteredSearch = e.target.value;
      this.listSearchStudents = this.students.filter((student) => {
        if (
          student.name.includes(this.enteredSearch) ||
          student.class.includes(this.enteredSearch)
        ) {
          return student;
        }
      });
    },
  },
};
</script>

<style scoped>
div {
  display: flex;
  justify-content: center;
  margin-top: 80px;
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
