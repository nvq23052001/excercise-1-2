<template>
  <nav>
    <ul>
      <li
        v-for="itemMenu in props.listMenu"
        :key="itemMenu.id"
        :class="{ active: selected === itemMenu.id }"
        @click="handleDisplay(itemMenu)"
      >
        {{ itemMenu.name }}
      </li>
    </ul>
    <h3 v-if="nameItem">Selected: {{ nameItem }}</h3>
  </nav>
</template>

<script setup>
import { ref, defineProps } from "vue";

const props = defineProps(["listMenu"]);

const nameItem = ref("");
const selected = ref(null);

function handleDisplay(item) {
  nameItem.value = item.name;
  selected.value = item.id;
}
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
>
