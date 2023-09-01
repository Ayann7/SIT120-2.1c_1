<script setup>
import { ref } from 'vue'

const message = ref('')
const checkedNames = ref([])
const selected = ref([])
const show = ref(false);
const mark = ref(false);
const elsee = ref(true)

const items = ref([
  { id: 1, name: 'Item 1', visible: true },
  { id: 2, name: 'Item 2', visible: false },
  { id: 3, name: 'Item 3', visible: true },
  { id: 4, name: 'Item 4', visible: true },
]);
</script>

<template>
  <p>Message is: {{ message }}</p>
  <input v-model="message" placeholder="edit me" /><br><br>

  <div>Checked names: {{ checkedNames }}</div>
  <input type="checkbox" id="Ayan" value="Ayan" v-model="checkedNames" />
  <label for="Ayan">Ayan</label>

  <input type="checkbox" id="Elon" value="Elon" v-model="checkedNames" />
  <label for="Elon">Elon</label>

  <input type="checkbox" id="Mark" value="Mark" v-model="checkedNames" />
  <label for="Mark">Mark</label><br><br>

  <span>Selected: {{ selected }}</span>
  <select v-model="selected" multiple>
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>

  <h1>v-if Example</h1>
  <h2 v-if="show">Task 2.1C!!</h2>
  <button @click="show = !show">Toggle</button><p></p><p></p>
  <h1>v-show Example</h1>
  <h2 v-show="mark">Task 2.1C!!</h2>
  <button @click="mark = !mark">Toggle</button>

  <div>
    <h1>List of Items</h1>
    <ul>
      <li v-for="item in items" :key="item.id">
        <template v-if="item.visible">
          {{ item.name }}
        </template>
      </li>
    </ul>
  </div>

  <button @click="elsee = !elsee">Toggle</button>

	<h1 v-if="elsee">The value is truthy!</h1>
	<h1 v-else>"Not truthy anymore :("</h1>
</template>
