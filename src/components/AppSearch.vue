<template>
   <form class="row gy-2 gx-3 align-items-center justify-content-center pt-5 " @submit.prevent=searchCharacters()>
  <div class="col-auto">
    <label class="visually-hidden" for="autoSizingInput">Name</label>
    <input type="text" class="form-control" id="autoSizingInput" placeholder="Jane Doe">
  </div>
  
  <div class="col-auto">
    <label class="visually-hidden" for="autoSizingSelect">Preference</label>
    <select class="form-select" id="searchStatus" v-model="search">
      <option selected value=" ">Cerca</option>
      <option :value="status" v-for="(status,index) in statusOption" :key="index">{{status}}</option>
      
    </select>
  </div>
  
  <div class="col-auto">
    <button type="submit" class="btn btn-primary">Submit</button>
  </div>
</form>
</template>

<script>
    export default {
        name:'AppSearch',
        data() {
          return {
              statusOption: [
                'Breaking Bad','Better Call Saul'
              ],
              search: ''
          }
        },
        methods: {
          searchCharacters(){
            this.$emit('filterchar',this.search);

          }
        },
    }
    
</script>

<style lang="scss" scoped>

</style>