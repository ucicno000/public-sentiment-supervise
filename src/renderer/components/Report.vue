<template>
  <div id="report">
      <div class="main_top">
          <el-date-picker
            v-model="start_time"
            type="date"
            placeholder="选择日期">
          </el-date-picker>
          - <el-date-picker
            v-model="end_time"
            type="date"
            placeholder="结束日期">
          </el-date-picker>
      <el-button>搜索</el-button> 
      </div>

    <el-table
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="date"
        label="日期"
        width="180">
      </el-table-column>
      <el-table-column
        prop="name"
        label="姓名"
        width="180">
      </el-table-column>
      <el-table-column
        prop="address"
        label="地址">
      </el-table-column>
    </el-table>

  </div>
</template>

<script>

  export default {
    name: 'report',
    data(){
      return {
        start_time:'',
        end_time:'',
         tableData: [{
            date: '2016-05-02',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1518 弄'
          }, {
            date: '2016-05-04',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1517 弄'
          }, {
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄'
          }, {
            date: '2016-05-03',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1516 弄'
          }]      }
    },
    methods: {
      open (link) {
        //this.$electron.shell.openExternal(link)
      }
    }
  }
</script>

<style lang="scss">
  .main_top {background:yellow;}
</style>
