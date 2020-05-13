<template>
    <p v-if="meetings.length < 1" class="empty-table">
      Brak zaplanowanych spotkan.
    </p>
    <table v-else > 
  <colgroup>
    <col class="w">
    <col>
    <col>
    <col class="w1">
  </colgroup>      
        <thead>
        <h3>Zaplanowane zajecia ({{ meetings.length }})</h3>
        <tr>
            <th>Nazwa spotkania</th>
            <th>Opis</th>
            <th>Uczestnicy</th>
            <th></th>
        </tr>
        </thead>
        <tbody>

        <tr v-for="meeting in meetings" :key="meeting.name">
            <td>{{ meeting.name }}</td>
			<td>{{ meeting.description }}</td>			
			<td>
	        <p v-for="participant in meeting.participants" :key="participant" v-if="editing"> <ul><li>{{ participant }}<li></ul> </p>
			<p v-else><ul> <li>{{participant}}</li> </ul></p>          
            </td>
		    <td>		   
		        <button v-if="meeting.participants.indexOf(user) !== -1" @click="removeParticipant(meeting.name)" class="button button-outline">Wypisz sie</button>
		        <button v-else @click="addParticipant(meeting.name)" class="button button-outline">Zapisz sie</button>             
                <button v-if="meeting.participants.length == 0" @click="$emit('delete:meeting', meeting.name)">Usun puste spotkanie</button>
            </td>
        </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        props: ['meetings', 'user'],
		    data() {
                return {
            editing: null
		    };
        },
	methods: {
		addParticipant(name) {
            for (var i=0; i<this.meetings.length; i++)
                if (this.meetings[i].name==name) {	
			        this.editing=true		
		            this.meetings[i].participants.push(this.user)
			        this.editing=null		
			    }
			},
		removeParticipant(name) {
			for (var i=0; i<this.meetings.length; i++)
				if (this.meetings[i].name==name) {	
					this.editing=true		
					this.meetings[i].participants.splice(this.meetings[i].participants.indexOf(this.user), 1)
					this.editing=null		
				}
			},				
	    },
	}
</script>
