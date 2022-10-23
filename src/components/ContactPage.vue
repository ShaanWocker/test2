<template>
    <HeaderPage/>
    <h1>Contact Page</h1>
    
</template>
<script>
import HeaderPage from './HeaderPage.vue'
import axios from 'axios'
    export default {
        name:'ContactPage',
        components:{
            HeaderPage
        },
        data(){
            return {
                resturant : {
                    name:'',
                    contact:'',
                    address:''
                }
            }
        },
        methods:{
            async addResturant(){
                const result = await axios.post(`http://localhost:3000/resturants`,{
                    name:this.resturant.name,
                    contact:this.resturant.contact,
                    address:this.resturant.address
                })
                if(result.status==201){
                    this.$router.push({name:'HomePage'})
                }
            }
        }
    }
</script>