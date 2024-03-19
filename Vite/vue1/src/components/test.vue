<script setup>
import { ref , onMounted , onUpdated ,computed } from 'vue'

defineProps({
  msg: String,
})

const name = ref('');
const count = ref(0)
const lastUpdated = ref('');
const currentTime = computed(() => lastUpdated.value );


// export default {
//   setup() {
//     const name = ref('');

//     const updateName = (event) => {
//       name.value = event.target.value;
//     };

//     return {
//       name,
//       updateName
//     };
//   },
// };
function reset() {
  name.value = '';
}

const upperCase = () => {
  name.value = name.value.toUpperCase();
  lastUpdated.value = new Date().toLocaleString(); 
};

const captalication = () => {
  // name.value = name.value.toUpperCase();
  name.value = name.value[0].toUpperCase() + name.value.slice(1);
  lastUpdated.value = new Date().toLocaleString();
}

    // Lifecycle hooks
    onMounted(() => {
      console.log('Component mounted');
      lastUpdated.value = new Date().toLocaleString();
    });

    onUpdated(() => {
      console.log('Component updated');
      lastUpdated.value = new Date().toLocaleString();
    });

</script>

<template>
  <div class="template">
    <p>Current Time: {{ currentTime }}</p>
    <p>Last Updated: {{ lastUpdated }}</p> 
  <h1>{{ msg }}</h1>
  <label for="name">Enter your name</label>
  <input type="text" id="name" v-model="name" @input="updateName">
  <p>Hello, {{ name }}!</p>

  <button @click="reset">Reset</button>
  <button @click="upperCase">Upper Case</button>
  <button @click="captalication">Captalization</button>
  </div>
 
</template>



<style>
.template {
  text-align: center;
  margin-top: 50px;
}

button {
  margin: 10px;
  padding: 8px 16px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

button:hover {
  background-color: #0e3d10;
}

</style>
