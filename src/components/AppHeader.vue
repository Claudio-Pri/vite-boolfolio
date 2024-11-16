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
		<nav>
			<ul>
			<li>
				<router-link :to="{ name: 'home' }" class="nav-link">
 					Home
 				</router-link>
			</li>
			<li>
				<router-link :to="{ name: 'about' }" class="nav-link">
					Chi siamo
 				</router-link>
			</li>
			<li>
				<router-link :to="{ name: 'projects' }" class="nav-link">
					Progetti
 				</router-link>
			</li>
		</ul>
		</nav>
	</header>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

header {
  	background-color: $mainDarkPurple;
  	display: flex;
	justify-content: center;
	align-items: center;
  	color: white;
  	text-align: center;
  	padding: 20px 0;
  	height: $headerHeight;
}

ul {
	display: flex;
	justify-content: center;
	align-items: center;
	list-style: none;
	li {
		margin: 0 5px;
		.nav-link {
			padding: 5px 10px;
			text-decoration: none;
			color: white;
			display: inline-block;
		}
	}
}

</style>
