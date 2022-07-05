<template>
  <div>
    <el-table :data="list" stripe style="width: 100%">
      <el-table-column prop="id" label="序号" width="100"> 
      </el-table-column>
      <el-table-column prop="bookname" label="书名" width="150">
      </el-table-column>
      <el-table-column prop="author" label="作者" width="250">
      </el-table-column>
      <el-table-column prop="publisher" label="出版商" width="250">
      </el-table-column>
      <el-table-column prop="appkey" label="操作" width="150">
        <button @click="del(id)">删除</button>
        <button @click="getmore(id)">详情</button>
      </el-table-column>
    </el-table>
  </div>
</template> 

<script>
import axios from 'axios';
export default {
  data() {
    return {
    };
  },
  props: {
    list:{
        type:Array,
        default:()=>([])
    }
  },
  methods:{
    //使用ele表格样式，没有经过v-fot遍历，获取不了按钮的id值
    getmore(val){
      axios({
        url:'http://www.liulongbin.top:3006/api/getbooks',
        method: 'GET',
        params:{
          //传参获取表格对应行的id，返回满足条件的数据
          id:val
        }
      }).then(res=>{
        // console.log(res.data.data);
        //渲染到页面上
        this.$parent.list= res.data.data
      })
    },
    del(id){
      const index = this.$parent.list.findIndex((ele)=>ele.id==id);
      this.$parent.list.splice(index,1);
    }
  }
};
</script>

<style></style>
