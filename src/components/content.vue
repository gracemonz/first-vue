<template>
   <div>

	   <div v-for="film in films">
		   <div>
			   {{film.title}}
		   </div>
		   <div>
			   {{film.description}}
		   </div>
		   <div>
			   {{film.director}}
		   </div>
		   <div>
			   {{film.producer}}
		   </div>
		   <div>
			   {{film.release_date}}
		   </div>
		   <div>
			   {{film.rt_score}}
		   </div>
   		</div>
   </div>
</template>

<script>
import Axios from 'axios'
export default {
	name: 'MainContent',
	mounted(){
		Axios.get(this.BaseUrl+'/films?limit=10').then(
			(response) => {
				this.films = response.data
			}
		)
		Axios.get(this.BaseUrl+'')
	},
	data(){
		return {
			BaseUrl: 'https://ghibliapi.herokuapp.com',
			
			films: {}
		}	
	}
}
</script>