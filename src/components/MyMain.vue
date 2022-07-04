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
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    list:{
        type:Array,
        default:()=>([])
    }
  }
};
</script>

<style></style>
