<template>
  <div>
    <!-- head -->
    <input type="text" placeholder="搜索——书本名称">
    <!-- main -->
    <el-table :data="tableData" stripe style="width: 100%">
      <el-table-column prop="id" label="序号" width="100"> </el-table-column>
      <el-table-column prop="bookname" label="书名" width="150"> </el-table-column>
      <el-table-column prop="author" label="作者" width="250"> </el-table-column>
      <el-table-column prop="publisher" label="出版商" width="250"> </el-table-column>
      <el-table-column prop="appkey" label="操作" width="150"> </el-table-column>
    </el-table>
    <!-- foot -->
    <input type="text" placeholder="书名"><br>
    <input type="text" placeholder="作者"><br>
    <input type="text" placeholder="出版社"><br>
    <button>新增</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [
        {
          id:1,
          bookname: '书名 ',
          author: '作者',
          publisher:'出版方',
          appkey:'7250d3eb-18e1-41bc-8bb2-11483665535a',
        },
      ],
    };
  },
};
</script>
