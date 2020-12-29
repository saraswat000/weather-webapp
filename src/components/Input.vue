<template>
  <div class="container">
    <section>
    <b-field label="Country"  >
        <b-input v-model="country" placeholder="Enter the Country Name" required></b-input>
    </b-field>
    <b-field label="City" >
        <b-input v-model="city" placeholder="Enter the City Name" required></b-input>
    </b-field>
    <b-button type="is-primary" @click="getWeather" :disabled="!city || !country" outlined>Get Weather Report</b-button>
    </section>
    <div v-if="check">
        <Modal :check="check" :data="weatherData" v-on:close="closeModal"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Modal from './Modal.vue'


const API_KEY="fe6b4f221e3b68d9fef20e9fb393b14a"

export default {

    data(){
        return {
            weatherData : null,
            check : false,
            city : null,
            country : null
        }
    },
    components : {
        Modal
    },
    methods : {
        getWeather(){
            axios.get(`http://api.openweathermap.org/data/2.5/weather?q=${this.city},${this.country}&appid=${API_KEY}`)
            .then( snapshot => {
                this.weatherData = snapshot.data;
                console.log(this.weatherData)
                this.check = true
            })
            .catch(() => console.log("Invalid data"));
            // console.log(snapshot);
        },
        closeModal(){
            this.country=null,
            this.city=null
            this.check=!this.check
        }
    }

}
</script>

<style>

</style>