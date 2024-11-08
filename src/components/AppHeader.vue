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
  background-color: $mainBgColor;
  text-align: center;
  padding: 20px 0;
}

</style>
