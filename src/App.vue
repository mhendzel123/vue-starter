

<template>
  <div>
  
	<h1>Witaj w systemie zapisow</h1>
	
	<div v-if="authenticatedUsername">
	<h3> zalogowany jako {{ authenticatedUsername }} </h3>
	<a @click="logMeOut()">wyloguj</a>
	
		
	</div>

	


	<div v-else>
			<input type="email" v-model="email">
	<button @click="logMeIn()">Zaloguj sie</button>
		
	</div>

		
  </div>
</template>



<script>

export default {
	data() {
 		return {
 			email: '',
 			authenticatedUsername: ''
 		};

 		
 	},
 	methods: {
  		logMeIn() {
    		this.authenticatedUsername = this.email;
    		this.email = '';
  		},
  		 	logMeOut() {
 		this.autenticatedUsername = '';
 		}
	}
}

</script>



<style>

</style>
