
  <script setup>
 import { ref } from 'vue';


    const selectedColor = ref('white');

   

  </script>
  
  <template>
    <div class="template">
      <label for="colorSelect">Select Text Color:</label>
      <select id="colorSelect" v-model="selectedColor">
        <option value="red">Red</option>
        <option value="green">Green</option>
        <option value="blue">Blue</option>
        <option value="cyan">Cyan</option>
        <option value="purple">Purple</option>
        <option value="Orange">Orange</option>
      </select>
  
      <h1><p :style="{ color: selectedColor }">Text color will change</p></h1>
    </div>
  </template>


  <style>
  .template {
  text-align: center;
  margin-top: 50px;
}

  </style>