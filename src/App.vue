<template>
<<<<<<< HEAD
    <div>
        <h1>Witaj w systemie do zapisów na zajęcia</h1>

        <div v-if="authenticatedUsername">
            <h2>Witaj {{ authenticatedUsername }}</h2>
            <a @click="logMeOut()">Wyloguj</a>
        </div>

        <div v-else>
            <login-form @login="logMeIn($event)" button-label="Wejdź"></login-form>
        </div>

    </div>
=======
<div>

	<h1>Witaj w systemie zapisow</h1>	
		
	<div v-if="authenticatedUsername">
		<h3>Zalogowany jako: {{ authenticatedUsername }}</h3>
		<a @click="logMeOut()">Wyloguj</a>
	</div>

	<div v-else>
		<login-form @login="logMeIn($event)"></login-form>		
	</div>
	
</div>
>>>>>>> 815caf2d8e7d9895b2f021217e38d6fbc2621f07
</template>


<script>
<<<<<<< HEAD
    import "milligram";
    import LoginForm from "./LoginForm";

    export default {
        components: {LoginForm},
        data() {
            return {
                authenticatedUsername: '',
            }
        },
        methods: {
            logMeIn(username) {
                this.authenticatedUsername = username;
            },
            logMeOut() {
                this.authenticatedUsername = '';
            }
        }
    }
</script>
=======
import "milligram";
import LoginForm from "./LoginForm";

export default {
	components: {LoginForm},
	data() {
		return {
			email: '',
			authenticatedUsername: ''
		};
	},
	methods: {
		logMeIn(username) {
			this.authenticatedUsername = username;
		},
		logMeOut() {
			this.authenticatedUsername = '';
		}
	}
}
</script>



<style>
</style>
>>>>>>> 815caf2d8e7d9895b2f021217e38d6fbc2621f07
