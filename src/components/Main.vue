<template>
  <div>
    <el-button @click="cachData">缓存</el-button>
    <el-button @click="getData" type="primary">获取</el-button>
    <el-button :plain="true" @click="open">打开消息提示</el-button>
    <p>这里是首页，可以放置一些公司的相关信息，简介等资料</p>
  </div>

</template>
<script>
export default {
  name: 'Main',
  data () {
    return {}
  },
  methods:{
    cachData(){
      sessionStorage.setItem('currentUserName',"wc")
    },
    open() {
      this.$message('这是一条消息提示');
    },

    getData(){
      let currentUserName = sessionStorage.getItem('currentUserName')
      this.$message.error(currentUserName)
    }

  }
}
</script>
<style>
#main {
  color: red;
}
#main p {
  background: #bbffaa;
}
</style>
