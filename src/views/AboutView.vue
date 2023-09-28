<template>
  <div class="about">
    <h5>Project Demos</h5>

    <!-- Handling User Inputs Example -->
    <div>
      <h2>Handling User Inputs</h2>
      <input type="text" v-model="message" placeholder="Type something...">
      <p>You typed: {{ message }}</p>
    </div>

    <!-- v-if Example -->
    <div>
      <h2>Toggle v-if Condition</h2>
      <label>
        <input type="checkbox" v-model="showExtraContent"> Show Extra Content
      </label>
    </div>
    

    <div v-if="showExtraContent">
      <h2>Show Me If v-if is True</h2>
      <p>This content will only be displayed if 'showExtraContent' is true.</p>
    </div>

    <!-- v-for Example -->
    <div>
      <h2>v-for Example</h2>
      <ul>
        <li v-for="(item, index) in items" :key="index">
          {{ item }}
        </li>
      </ul>
    </div>

    <div class="task task1b">
      <h2>Raw HTML</h2>
      <p>Using text interpolation: {{ rawHtml }}</p>
      <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    </div>

    <div class="task task2">
      <h2>Methods</h2>
      <button @click="incrementCounter" class="button">Increment Counter</button>
      <button @click="decrementCounter" class="button">Decrement Counter</button>
      <p> {{ task2Counter }}</p>
    </div>

    <div class="task task3">
      <h2>Reactivity Fundamentals with ref()</h2>
      <div class="count-display">{{ count }}</div>
      <button @click="increment" class="button">Increment</button>
    </div>
    
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Data properties for Task 1b - Raw HTML
const rawHtml = ref('<span style="color: red;">I\'m red!!</span>') // Escaped the inner single quotes


// Handling User Inputs
const message = ref('');

// v-if Example
const showExtraContent = ref(true);

// v-for Example
const items = ref(['Item 1', 'Item 2', 'Item 3']);

// Task 2 - Methods
const task2Counter = ref(0);

// Function to increment the counter for Task 2
function incrementCounter() {
  task2Counter.value++
}

// Function to decrement the counter for Task 2
function decrementCounter() {
  if (task2Counter.value > 0) {
    task2Counter.value--
  }
}

// Task 3 - Reactivity Fundamentals with ref()
const count = ref(0)

// Function to increment the counter for Task 3
function increment() {
  count.value++
}

// Task 5a - Binding HTML Classes
const isActive = ref(false)

// Function to toggle the isActive class for Task 5a
function toggleClass() {
  isActive.value = !isActive.value
}

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    flex-direction: column; /* Center content vertically */
  }
}
</style>
