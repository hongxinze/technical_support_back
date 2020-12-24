<template>
  <el-container>
    <!--顶端栏头部-->
    <el-header>
      <!--logo和项目名称-->
      <div class="left_box">
        <!--这里这张图片是我省事直接用了头像的图片，可替换-->
        <img src="../assets/img/avatar.jpg">
        <!--后台管理系统-->
        <span>技术支持需求管理系统后台</span>

        <span>Admin</span>
      </div>

      <div class="right_box">
        <el-dropdown>

          <!--点击头像触发下拉菜单-->
          <img src="../assets/img/avatar.jpg">
          <!--下拉菜单-->
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item icon="el-icon-house">系统首页</el-dropdown-item>
            <el-dropdown-item icon="el-icon-ship">交流讨论</el-dropdown-item>
            <el-dropdown-item icon="el-icon-switch-button">退出登录</el-dropdown-item>

          </el-dropdown-menu>
        </el-dropdown>
      </div>
    </el-header>


    <el-container>

      <!--左边导航栏-->
      <el-nav width="200px">
        <el-menu :default-openeds="['1', '3']">
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>导航一</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title"><i class="el-icon-menu"></i>导航二</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="2-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="2-4">
              <template slot="title">选项4</template>
              <el-menu-item index="2-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i>导航三</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="3-1">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="3-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="3-4">
              <template slot="title">选项4</template>
              <el-menu-item index="3-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
      </el-nav>

      <!--主体部分-->
      <el-main>
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
<!--          <el-menu-item index="1">处理中心</el-menu-item>-->
<!--          <el-submenu index="2">-->
<!--            <template slot="title">我的工作台</template>-->
<!--            <el-menu-item index="2-1">选项1</el-menu-item>-->
<!--            <el-menu-item index="2-2">选项2</el-menu-item>-->
<!--            <el-menu-item index="2-3">选项3</el-menu-item>-->
<!--            <el-submenu index="2-4">-->
<!--              <template slot="title">选项4</template>-->
<!--              <el-menu-item index="2-4-1">选项1</el-menu-item>-->
<!--              <el-menu-item index="2-4-2">选项2</el-menu-item>-->
<!--              <el-menu-item index="2-4-3">选项3</el-menu-item>-->
<!--            </el-submenu>-->
<!--          </el-submenu>-->
          <el-menu-item index="1" >首页</el-menu-item>
<!--          <el-menu-item index="3" disabled>消息中心</el-menu-item>-->
<!--          <el-menu-item index="4"><a href="https://www.ele.me" target="_blank">订单管理</a></el-menu-item>-->
        </el-menu>

        <h1>欢迎来到首页</h1>
      </el-main>


    </el-container>
  </el-container>



</template>

<script>



export default {
  name: 'Home',
  data() {
    return {
      activeIndex: '1',
      activeIndex2: '1'
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    }
  }

}
</script>


<style lang="less" scoped>

.el-header{
  background-color: #001529;
  display: flex;
  justify-content: space-between;
  padding-left: 0;
  color: #FFFFFF;
  text-align: center;
  line-height: 60px;
  height: 20%;
  width: 100%;
  text-align: right;
  font-size: 12px;


  // 左边的logo和标题
  .left_box{
    display: flex;
    align-items: center;

    //log图像的大小与位置细节设置
    img{
      width: 60px;
      height: 60px;
      margin: 0px 0px 0px 0px;
    }
    // 标题
    span{
      margin-left: 15px;
    }
  }

  // 右边的登录头像和下拉框
  .right_box{



    .el-dropdown>img{
      width:60px;
      height: 60px;
      border-radius:50%;
      background-color: #FFFFFF;
      margin: 0px;
      background-size: contain;
    }
    // 标题
    span{

      margin-right: 15px;

    }
  }

}

.el-nav {
  background-color: #D3DCE6;
  color: #333;
  text-align: center;
  line-height: 200px;
  height: 80%;
  width: 20%;
}

.el-main {
  background-color: #E9EEF3;
  color: #333;
  text-align: center;
  line-height: 160px;
  width: 80%;
  height: 80%;
  margin: 0;
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-nav,
.el-container:nth-child(6) .el-nav {
  line-height: 260px;
}

.el-container:nth-child(7) .el-nav {
  line-height: 320px;
}

</style>
