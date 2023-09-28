<template>
  <div class="myDiv">
    <h1>Q&A</h1>
    <input type="text" v-model="shoppingitem" placeholder="Ask me anything...">
    <button @click="addItem">Ask</button>
    <ol>
      <li v-for="item in shoppinglist" :key="item.id">
        <input type="checkbox" v-model="item.status">
        <span :class="{ done: item.status }">{{ item.item }}</span>
        <button @click="removeItem(item)">Remove</button>
      </li>
      <h4 v-if="shoppinglist.length < 1">No questions yet.</h4>
    </ol>

        <h0>Screenshot your questions and send them below!</h0>

    <!-- Contact Section -->
    <section class="contact">
      <h2>Contact Me</h2>
      <p>
        You can reach out to me via email at <a href="mailto:s223751883@deakin.edu.au">s223751883@deakin.edu.au</a>.
        I'm also active on Instagram and GitHub. Feel free to connect with me on these platforms.
      </p>
    </section>

    <!-- Additional Details Section -->
    <section class="additional-details">
      <ul>
        <li>Instagram:  <a href="https://www.instagram.com/willsmith"> Insta Profile</a></li>
        <li>GitHub: <a href="https://github.com/MohamedDeakin"> GitHub Profile</a></li>
      </ul>
    </section>

  </div>
</template>

<script setup>
import { ref } from 'vue';

const itemId = ref(0);
const shoppingitem = ref('');
const shoppinglist = ref([]);
const shopped = ref(false);

function addItem() {
  shoppinglist.value.push({
    id: itemId.value++,
    item: shoppingitem.value,
    status: shopped.value,
  });
  shoppingitem.value = '';
}

function removeItem(itemToRemove) {
  shoppinglist.value = shoppinglist.value.filter((item) => item !== itemToRemove);
}



</script>

<style scoped>
.myDiv {
  border: 2px solid #007BFF;
  background-color: #f5f5f5;
  text-align: center;
  padding: 20px;
  border-radius: 10px;
}

input[type="text"] {
  padding: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #007BFF;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

ol {
  list-style: none;
  padding: 0;
  text-align: left;
  margin-top: 10px;
}

li {
  display: flex;
  align-items: center;
  margin: 5px 0;
}

.done {
  text-decoration: line-through;
  color: #555;
}

button {
  background-color: #ff4646;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-left: 10px;
}

button:hover {
  background-color: #cc0000;
}
</style>
