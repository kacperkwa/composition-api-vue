<template>
  <section class="container">
    <UserData :first-name="firstName" :last-name="lastName" :age="age">
    </UserData>
    <button @click="setNewAge()">Change Age</button>
    <div>
      <input type="text" placeholder="First Name" v-model="firstName" />
      <input type="text" placeholder="Last Name" ref="lastNameInput" />
      <button @click="setLastName">Set Last Name</button>
    </div>
  </section>
</template>

<script setup>
import { ref, watch } from 'vue';
import UserData from './components/UserData.vue';

// const userName = ref('Kacper');
const age = ref(26);
const firstName = ref('');
const lastName = ref('');
const lastNameInput = ref(null);
// const user = reactive({
//   name: 'Kacper',
//   age: 26,
// });

watch([age], (newValues, oldValues) => {
  console.log('Old age: ' + oldValues[0]);
  console.log('New age: ' + newValues[0]);
  console.log('Old name: ' + oldValues[1]);
  console.log('New name: ' + newValues[1]);
});

const setLastName = () => {
  lastName.value = lastNameInput.value.value;
};

const setNewAge = () => {
  age.value += 2;
};
// const setFirstName = (event) => {
//   firstName.value = event.target.value;
// };
// const setLastName = (event) => {
//   lastName.value = event.target.value;
// };
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
button {
  cursor: pointer;
}
</style>
