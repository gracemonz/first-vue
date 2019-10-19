
<template>
    <div>
        <li v-for="qoute in Qoutes">
           <p> {{qoute.en}}</p>
        </li>
        <div>
            {{RandomQoutes}}
        </div>
    </div>
</template>

<script>
import VueAxios from 'vue-axios'
import axios from 'axios'

export default {
    name: 'sample',
    mounted(){
        axios.get('https://programming-quotes-api.herokuapp.com/quotes/en').then(
            (response)=> {
                this.Qoutes = response.data;
            }
        )

        axios.get('https://programming-quotes-api.herokuapp.com/quotes/random').then(
            (response) => {
                this.RandomQoutes = response.data;
            }
        )
    },
    data: function(){
        return {
            Qoutes: [{
                qoute:{}
            }],
            RandomQoutes:{}
        }
    }      
}
</script>