<template>
  <div>
    <input type="text" placeholder="搜索——书本名称" v-model="bookname" @keydown.enter='findFn'>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            bookname:'',
        }
    },
    methods:{
        findFn(){
            console.log(111);
            if(this.bookname==''){return alert('你是傻子么')}
            axios({
                url:'http://123.57.109.30:3006/api/getbooks',
                method: 'GET',
                params:{
                    bookname: this.bookname
                }
            }).then(res=>{
                console.log(res);
                this.$parent.list= res.data.data
            })
        }
    }
}
</script>

<style>

</style>