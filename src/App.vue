
<template>
  <div>
	<h1>twoj email to {{ email }}</h1>
	<h3>email  {{ email }}</h3>
			<input type="email"
			v-model="email">
  </div>
</template>



<script>
export default {
 data() {
 	return {
 		email: ''
 		};
 	}
}
</script>



<style>

</style>
