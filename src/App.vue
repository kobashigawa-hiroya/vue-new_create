<template>
 <div id="app">
    <h1>メモ  帳</h1>
    <div>
      <label for="title">タイトル：</label>
      <input type="text" v-model="title" placeholder="タイトル">
    </div>
    <div class="text">
      <div class="form-floating">
        <textarea style="max-width:380px;margin-bottom:10px" v-model="body" class="form-control"></textarea>
  <label for="floatingTextarea">内容</label>
  <button class="btn btn-primary" @click="addList">メモ追加</button>
      </div>
    </div>
    <!-- <ul v-for="(list, i) in lists" v-bind:key="i">
      <li>id: {{ i }},title: {{ list.title }}, content: {{list.body }} <button @click="deleteList">削除</button></li>
    </ul> -->
    <div class="card" style="max-width:380px">
  <h5 class="card-header"  style="margin:15px" v-for="(list, i) in lists" v-bind:key="i">
      <p>タイトル： {{ list.title }}</p>
          <h5 class="card-title">内容: {{list.body }} </h5>
          <button class="btn btn-danger" @click="deleteList">削除</button>
</h5>
</div>
<br>
  </div>
  </template>

<script>

export default {
  data: () => ({
    lists: [
    ],
  }),
methods: {
  addList: function() {
    
    if(this.title === "" || this.body === "")return
    this.lists.push({title: this.title, body: this.body})
    this.tile = "",
    this.body = ""
  },
  deleteList: function(i) {
    this.lists.splice(i,1) 
  }
}
    } 
</script>

<style>
  #app {
    text-align: center;
  }

  .text {
    display: inline-block;
    text-align: center;
  }

  div.card {
        margin: 0 auto;
        background-color: wheat;;
  }
  .form-floating {
    margin: 30px 15px;
  }
</style>

