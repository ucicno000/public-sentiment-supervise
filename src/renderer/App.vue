<template>
  <div id="app">
    <el-container style="height: 500px; border: 1px solid #eee">
  <el-aside :style="{'height':winHeight+'px'}">
      <el-menu :default-openeds="['1','2', '3']">
        <el-submenu index="1">
          <template slot="title"><i class="el-icon-location-outline"></i>起始页面</template>
          <el-menu-item index="2-4-1"><router-link to='home'>欢迎页面</router-link></el-menu-item>

        </el-submenu>
        <el-submenu index="2">
          <template slot="title"><i class="el-icon-menu"></i>舆情报告</template>
          <el-menu-item index="2-4-1"><router-link to='report'>全部舆情</router-link></el-menu-item>
          <el-menu-item index="2-4-1"><router-link to='report?id=1'>正面舆情</router-link></el-menu-item>
          <el-menu-item index="2-4-1"><router-link to='report?id=2'>负面舆情</router-link></el-menu-item>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title"><i class="el-icon-setting"></i>舆情设置</template>
            <el-menu-item index="3-1">
              <router-link to='keywords'>舆情关键字设置</router-link>
            </el-menu-item>
            <el-menu-item index="3-2">
                <router-link to='alarm'>舆情报警设置</router-link>
            </el-menu-item>
        </el-submenu>
      </el-menu>
    </el-aside>
  
  <el-container class="main" :style="{'height':winHeight+'px'}">
     <router-view></router-view>
  </el-container>

  <el-dialog
      title="提示"
      :visible.sync="dialogVisible"
      width="30%"
      :show-close=false
      :close-on-press-escape=false
      :close-on-click-modal=false
      :center=true
       >
        <el-form ref="form" :model="form" label-width="80px">
        <el-form-item label="用户名">
          <el-input v-model="form.name"></el-input>
        </el-form-item>
           <el-form-item label="密码">
          <el-input v-model="form.name"></el-input>
        </el-form-item>
        </el-form>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">登录</el-button>
      </span>
    </el-dialog>
</el-container>
   
  </div>
</template>

<script>
  export default {
    name: 'public-sentiment-supervise',
    data() { 
      return {
       winHeight:document.documentElement.clientHeight,
       dialogVisible:true,
       form:{}
      }
    },
    mounted(){
       window.onresize=()=>{ 
        this.winHeight=document.documentElement.clientHeight;
      }
    }

  }
</script>

<style lang="scss">

*{

  margin:0px;
  padding:0px;
}

.el-aside {

    width: 200px!important;
    background: #eee;

    a{
     color: #333; 
     display: block;
     text-decoration: none;     

    }
    .el-menu{
      background: #eee;
    }
   
  }

  .el-container{

      overflow-y: hidden;
     overflow-x: hidden;

    // padding:10px;

    width: 100%;
    
  }
  .main{
    padding:10px;
    overflow-x:hidden;
    overflow-y:auto;
  }
  .v-modal{

    opacity:1;
    background-image: url(./assets/login_bg.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    
  }


</style>