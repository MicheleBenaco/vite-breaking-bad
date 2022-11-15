<template>
    <div class="row pt-5">
        <div class=" col-12 col-sm-6 col-md-4 col-lg-3  p-5" v-for="(item,index) in characters" :key="id" >

            <div class="character ">
                    <img :src="item.img" alt="img" class="">
                    <h1>{{item.name}}</h1>
                    <h3>{{item.birthday}}</h3>
                    <h3>{{item.nickname}}</h3>
                    <h3>{{item.status}}</h3>
                    <h3>{{item.category}}</h3>
            </div>
           
        </div>
       
    </div>
</template>





<script>
    export default {
        name:'CharacterList',
        props:['characters']
    }
</script>

<style lang="scss" scoped>
    .character{
        text-align: center;
        h3{
            padding-top: 5px;
            font-weight: 700;
        }

        h1{
            color: green;
        }
       

       


        img{
            width:  250px;
            height: 250px;
            border-radius: 50%;
            object-fit: cover;
            overflow: hidden;    
         
        }
    }

</style>