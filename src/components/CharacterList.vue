<template>
    <div class="row">
        <div class=" col-12 col-sm-6 col-md-4 col-lg-3">

            <div class="character" v-for="(item,index) in characters" :key="id">
                    <img :src="item.img" alt="">
                    <h3>{{item.name}}</h3>
                    <h3>{{item.birthday}}</h3>
                    <h3>{{item.nickname}}</h3>
                    <h3>{{item.status}}</h3>
            </div>
           
        </div>
       
    </div>
</template>

// "char_id": 1,
// "name": "Walter White",
// "birthday": "09-07-1958",
// "occupation": [
// "High School Chemistry Teacher",
// "Meth King Pin"
// ],
// "img": "https://images.amcnetworks.com/amc.com/wp-content/uploads/2015/04/cast_bb_700x1000_walter-white-lg.jpg",
// "status": "Presumed dead",
// "nickname": "Heisenberg",

<script>
    export default {
        name:'CharacterList',
        props:['characters']
    }
</script>

<style lang="scss" scoped>

</style>