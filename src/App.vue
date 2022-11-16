<template>
  <AppHeader/>
  <main class="container">
    <AppSearch @filterchar="getCharacter" />
    <CharacterList :characters="CharacterList"/>
  </main>
  

</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppSearch from './components/AppSearch.vue';
import CharacterList from './components/CharacterList.vue';
  export default {
    components:{
    AppHeader,
    AppSearch,
    CharacterList
},
data() {
  return {
    apiUrl :'https://www.breakingbadapi.com/api/characters',
    CharacterList:[],
    searchStatus : '',
  }
},methods: {
    getCharacter(status){
      if(status){
        this.apiUrl = this.apiUrl + '?category'+status;
      }
      axios.get(this.apiUrl).then(
        (res)=>{ 
          this.CharacterList = [...res.data];

        }
      )

    }
},
created() {
    this.getCharacter()
},
   
  }
</script>

<style lang="scss" scoped>

</style>