@import url('main.css');

<template>
  <div class="portfolio">
    <header>
      <h1>My Portfolio</h1>
    </header>

        <!-- About Me Section -->
    <section class="about-me">
      <h2>About Me</h2>
    <div>
      <ul>
        <li v-for="(item, index) in items" :key="index">
          {{ item }}
        </li>
      </ul>
    </div>
    </section>

    <!-- Projects Section -->
    <section class="projects">
      <h2>Projects</h2>
      <div class="project">
        <h3>First Project</h3>
        <p> This project entailed the creation of an HTML webpage, accompanied by the application of CSS styles, while also serving as an insightful introduction to the world of GitHub. Within the realm of HTML, the task required the skillful inclusion of various essential tags such as 'img' for images, tables, forms, and a host of others. What truly captured my fascination was the transformation that took place as I watched my images come to life and my tables take on a polished appearance, all thanks to the use of the 'style' tag tucked away within the 'head' section. Moreover, the functionality of my form was brought to life, complete with multiple input fields and a submit button of type="submit." Delving into the realm of CSS, I applied artful styling to my HTML creation, neatly connecting it to an external .css file housing meticulously crafted styles for tables, buttons, and other elements, all skillfully facilitated by the 'link' tag. Lastly, my initiation into the realm of Git and GitHub was a seamless experience. Navigating through the repository, I found myself easily uploading and submitting my code, all of which made for an efficient and straightforward process.
        </p>
      </div>
      <div class="project">
        <h3>Latest Project</h3>
        <p>In the exploration of Vue 3 concepts, the focus was on various aspects. Starting with template syntax, it allowed for dynamic data display through text interpolation, raw HTML rendering, attribute bindings, and JavaScript expressions within double curly braces. Methods like 'incrementCounter' and 'decrementCounter' were used for data modification. Reactivity fundamentals, including 'ref()' and 'script setup', created reactive data references and enhanced code readability. Computed properties helped calculate and cache values based on reactive data. Class and style bindings enabled dynamic styling with 'v-bind:class' and inline style binding with 'v-bind:style'. List rendering involved 'v-for' techniques for objects, numeric ranges, template elements, conditional rendering, and components. Event handling responded to events with both inline handlers and method calls. Form input bindings simplified data binding between form elements and component data using 'v-model'. Watchers reacted to data changes and executed custom logic when data changed. Components like 'TaskItem', 'BlogPost', 'Home', 'About', and 'NotFound' contributed to modular and maintainable applications. Lastly, the router allowed client-side routing, enabling single-page applications with navigation based on current routes. The gradual implementation of these concepts, influenced by workshop experiences, helped me grow from the first to this latest project.     </p>
      </div>
    </section>

    <section class="project-table">
      <h2>Video Presentation</h2>
      <table>
        <thead>
          <tr>
            <th>Project Name</th>
            <th>Link</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>First Project</td>
            <td><a href="https://video.deakin.edu.au/media/t/1_gikpqer3" target="_blank">https://video.deakin.edu.au/media/t/1_gikpqer3</a></td>
          </tr>
          <tr>
            <td>Latest Project</td>
            <td><a href="https://youtu.be/YKP2Hs8xLY8" target="_blank">https://youtu.be/YKP2Hs8xLY8</a></td>
          </tr>
        </tbody>
      </table>
    </section>

  </div>
</template>

<script setup>
import { ref } from 'vue';

// Handling User Inputs
const message = ref('');

// v-if Example
const showExtraContent = ref(true);

// v-for Example
const items = ref(['Mohamed El-Hassan', '22', 'Bachelor of Information Technology']);
</script>

<style scoped>

/* Media Queries for Responsive Design */
@media (max-width: 768px) {
  .projects {
    padding: 10px;
  }
  
  .project h3 {
    font-size: 1rem;
  }
}

</style>
