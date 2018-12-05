<template>
   <div>
    <City-header></City-header>
    <City-search :cities="cities"></City-search>
    <City-list :cities="cities" :hot="hotCities" :letter="letter"></City-list>
    <City-alphabet :cities="cities" @change="handleLetterChange"></City-alphabet>
   </div>
</template>
<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'

import axios from 'axios'

export default {
    name:'City',
    components:{
         CityHeader,CitySearch,CityList,CityAlphabet
    },
    mounted(){
        this.getCityInfo()
    },
    methods:{
        getCityInfo(){
            axios.get('/api/city.json')
            .then(this.handleGetCityInfoSucc)
        },
        handleGetCityInfoSucc(res){
            res = res.data
            if(res.ret && res.data){
                const data = res.data
                this.cities = data.cities
                this.hotCities = data.hotCities
            }
        },
        handleLetterChange(letter){
              this.letter = letter
        }
    },
    data(){
        return{
            cities:{},
            hotCities:[],
            letter:''
        }
    }

}
</script>
<style scoped lang="stylus">

</style>


