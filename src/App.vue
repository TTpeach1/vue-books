<template>
  <div>
    <!-- head -->
    <MyHead></MyHead>
    <!-- main -->
    <MyMain :list='list'></MyMain>
    <!-- foot -->
    <MyFoot></MyFoot>
  </div>
</template>

<script>
//引入axios
import axios from 'axios';
import MyHead from '@/components/MyHead'
import MyMain from '@/components/MyMain'
import MyFoot from '@/components/MyFoot'
export default {
  data() {
    return {
      list: [],
    };
  },
  components:{
    MyHead,
    MyMain,
    MyFoot
  },
  created(){
    axios({
      url:"http://123.57.109.30:3006/api/getbooks",
      method:"GET",
    }).then((res)=>{
      // console.log(res);
      this.list = res.data.data
    })
  }
};
</script>
