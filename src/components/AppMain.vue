<script>
export default {
  data() {
    return { 
      message: 'Vite Boolfolio Main'
    }
  }
}
</script>

<template>
	<main>
		<!-- router view -->
		<router-view></router-view>
	</main>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

</style>
