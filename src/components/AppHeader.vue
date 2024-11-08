<script>
export default {
  data() {
    return { 
      message: 'Vite Boolfolio Header'
    }
  }
}
</script>

<template>
  <header>
    <h4>
      {{ message }}
    </h4>
  </header>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

header {
  background-color: $mainDarkPurple;
  color: white;
  text-align: center;
  padding: 20px 0;
  height: $headerHeight;
}

</style>
