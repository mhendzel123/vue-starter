


<template>
  <div>
	<h1>Twoj email to: {{ email }}</h1>
	
	<div v-if="email.length < 10">Ale masz krotki adres!</div>
	<div v-else-if="email.length < 15">Twoj adres e-mail jest w sam raz.</div>
	<div v-else>Twoj adres e-mail jest stanowczo za dlugi.</div>
	
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
