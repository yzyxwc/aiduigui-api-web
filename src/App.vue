<template>
  <transition name="fade">
    <router-view v-if="noRefresh" ></router-view>
  </transition>
</template>

<script>
export default {
  name: 'App',
  provide() {
    return {
      reload: this.reload
    }
  },
  data() {
    return {
      noRefresh: true
    }
  },
  methods:{
    reload() {
      this.noRefresh = false
      this.$nextTick(function(){
        this.noRefresh = true
      })
    }
  }
}
</script>

<style>
.vue-treeselect__control{
  height: 20px !important
}

body .el-table th.gutter{
  display: table-cell!important;
}

body .el-table colgroup.gutter{
  display: table-cell!important;
}

</style>

