<script>
export default {
  data() {
    return { 
      message: 'Vite Boolfolio | Home Page'
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
}
</style>
