<script>
import axios from 'axios';
export default {
  data() {
    return { 
      message: 'Vite Boolfolio Main',
      projects: []
    }
  },
  mounted() {
    this.getProjects();
  },
  methods: {
    getProjects() {
      axios
          .get('http://127.0.0.1:8000/api/projects')
          .then((res) => {
            // console.log(res.data);
            this.projects = res.data.projects.data;
            console.log(this.projects);
          });
    }
  }
}
</script>

<template>
  <main>
      <div class="container">
        <h1>
          {{ message }}
        </h1>
      </div>
      <div class="container">
        <div v-for="project in projects" :key="project.id">
          <h3>
            {{ project.title }}
          </h3>
          <p v-if="project.type != null">
            {{ project.type.title }}
          </p>
          <p v-else>
            Nessuna categoria assegnata
          </p>
          <div class="container">
            <div v-for="technology in project.technologies" :key="technology.id">
              {{ technology.title }}
            </div>
          </div>
        </div>
      </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;


</style>
