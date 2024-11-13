<script>
import axios from 'axios';
export default {
  data() {
    return { 
      defaultUrl: 'http://127.0.0.1:8000/api/projects',
      message: 'Vite Boolfolio Main',
      projects: [],
      prevPage: [],
      nextPage: [],
      clickedBtn: false
    }
  },
  mounted() {
    this.getProjects(this.defaultUrl);
  },
  methods: {
    getProjects(url) {
      axios
          .get(url)
          .then((res) => {
            // console.log(res.data);
            this.projects = res.data.projects.data;
            console.log(this.projects);

            this.prevPage = res.data.projects.prev_page_url;
            this.nextPage = res.data.projects.next_page_url;

            this.clickedBtn = false;

          });
    },
    getPrevPage() {
      // console.log('getPrevPage');
      this.clickedBtn = true;

      this.getProjects(this.prevPage);
      // axios
      //     .get(this.prevPage)
      //     .then((res) => {
      //       // console.log(res.data);
      //       this.projects = res.data.projects.data;
      //       console.log(this.projects);

      //       this.prevPage = res.data.projects.prev_page_url;
      //       this.nextPage = res.data.projects.next_page_url;

      //       this.clickedBtn = false;

      //     });
    },
    getNextPage() {
      // console.log('getNextPage');
      this.clickedBtn = true;

      this.getProjects(this.nextPage);
      // axios
      //     .get(this.nextPage)
      //     .then((res) => {
      //       // console.log(res.data);
      //       this.projects = res.data.projects.data;
      //       console.log(this.projects);

      //       this.prevPage = res.data.projects.prev_page_url;
      //       this.nextPage = res.data.projects.next_page_url;

      //       this.clickedBtn = false;
      //     });
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
        <div class="my-row">

          <div class="my-col-6" v-for="project in projects" :key="project.id">

            <div class="my-card">

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

        </div>

        <div class="buttons">
          <!-- buttons da stilizzare -->
          <button @click="getPrevPage()" :disabled="prevPage == null || clickedBtn">
            &lt; Precedente
          </button>

          <button @click="getNextPage()" :disabled="nextPage == null || clickedBtn">
            &gt; Successiva
          </button>

        </div>

      </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;
main {
  background-color: $mainDarkBlue;
  color: white;
  padding: 50px 0;
  height: calc(100vh - ($headerHeight + $footerHeight));
  h1 {
    text-align: center;
    margin-bottom: 30px;
  }
  .my-card {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    height: 100%;
    margin: 0 20px;
    padding: 10px 20px;
    border: 2px solid $secondaryDarkPurple;
    border-radius: 10px;
    & > * {
      margin: 10px 0;
    }
  }
}

</style>
