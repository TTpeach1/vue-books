<template>
  <div>
    <input type="text" placeholder="书名" v-model="bookObj.bookname" /><br />
    <input type="text" placeholder="作者" v-model="bookObj.author" /><br />
    <input type="text" placeholder="出版社" v-model="bookObj.publisher" /><br />
    <button @click="add">新增</button>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      bookObj: {
        bookname: '',
        author: '',
        publisher: '',
      },
    };
  },
  methods: {
    add() {
      axios({
        url: 'http://www.liulongbin.top:3006/api/addbook',
        method: 'POST',
        data: {
          ...this.bookObj
          // bookname: this.bookname,
          // author: this.author,
          // publisher: this.publisher,
        },
      }).then((data)=>{
        alert(data.data.msg)
      })
      this.bookObj={}
    },
  },
};
</script>

<style></style>
