<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="app-container">
    <el-container>
      <el-header>
        <div class="header-content">
          <div class="logo">
            <img src="/src/assets/logo.svg" alt="智创未来科技" class="logo-img">
            <h1>智创未来科技</h1>
          </div>
          <el-menu
            mode="horizontal"
            :router="true"
            class="nav-menu"
            :ellipsis="false"
          >
            <el-menu-item index="/">首页</el-menu-item>
            <el-menu-item index="/about">关于我们</el-menu-item>
            <el-menu-item index="/products">产品服务</el-menu-item>
            <el-menu-item index="/contact">联系我们</el-menu-item>
          </el-menu>
        </div>
      </el-header>

      <el-main>
        <div class="main-content">
          <router-view></router-view>
        </div>
      </el-main>

      <el-footer>
        <div class="footer-content">
          <p>© 2024 智创未来科技有限公司 版权所有</p>
          <p class="icp">
            <a href="https://beian.miit.gov.cn/" target="_blank" rel="noopener noreferrer">
              京ICP备XXXXXXXX号-1
            </a>
            <span class="divider">|</span>
            <a href="http://www.beian.gov.cn/" target="_blank" rel="noopener noreferrer">
              <img src="https://www.beian.gov.cn/img/new/gongan.png" alt="公安备案图标" class="beian-icon">
              京公网安备 XXXXXXXXXXXX号
            </a>
          </p>
        </div>
      </el-footer>
    </el-container>
  </div>
</template>

<style scoped>
.app-container {
  min-height: 100vh;
  margin: 0;
  padding: 0;
}

.el-container {
  min-height: 100vh;
  margin: 0;
  padding: 0;
}

.el-header {
  background-color: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  position: fixed;
  width: 100%;
  z-index: 1000;
  height: 60px !important;
  padding: 0;
  margin: 0;
  top: 0;
}

.header-content {
  max-width: 1200px;
  margin: 0;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  height: 100%;
  padding: 0;
  margin-left: 30px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  margin: 0;
  padding: 0;
}

.logo-img {
  height: 40px;
  width: auto;
  margin: 0;
  padding: 0;
}

.logo h1 {
  margin: 0;
  padding: 0;
  font-size: 24px;
  color: #409EFF;
  font-weight: 600;
}

.nav-menu {
  border-bottom: none;
  background: transparent;
  margin-left: auto;
  margin-right: 20px;
}

.nav-menu :deep(.el-menu-item) {
  font-size: 16px;
  height: 60px;
  line-height: 60px;
}

.nav-menu :deep(.el-menu-item.is-active) {
  color: #409EFF;
  border-bottom: 2px solid #409EFF;
}

.el-main {
  padding-top: 80px;
  background-color: #f5f7fa;
  min-height: calc(100vh - 120px);
  margin: 0;
}

.main-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.el-footer {
  background-color: #303133;
  color: white;
  text-align: center;
  padding: 20px 0;
  margin: 0;
  min-height: 80px;
  display: flex;
  align-items: center;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  width: 100%;
}

.footer-content p {
  margin: 8px 0;
  color: #909399;
  line-height: 1.5;
}

.icp {
  font-size: 14px;
  margin-top: 10px;
}

.icp a {
  color: #909399;
  text-decoration: none;
  transition: color 0.3s;
  display: inline-flex;
  align-items: center;
}

.icp a:hover {
  color: #409EFF;
}

.divider {
  margin: 0 10px;
  color: #909399;
}

.beian-icon {
  height: 16px;
  margin-right: 5px;
  vertical-align: middle;
}

@media screen and (max-width: 768px) {
  .header-content,
  .main-content,
  .footer-content {
    padding: 0 15px;
  }
}
</style>
