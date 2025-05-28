<template>
  <div class="products-container">
    <!-- 产品服务头部 -->
    <div class="products-header">
      <h1>产品服务</h1>
      <p class="subtitle">创新科技，引领未来</p>
    </div>

    <!-- 产品展示区 -->
    <div class="products-section">
      <h2>核心产品</h2>
      <el-row :gutter="30">
        <el-col :span="8" v-for="(product, index) in products" :key="index">
          <el-card class="product-card" :body-style="{ padding: '0px' }">
            <img :src="product.image" class="product-image">
            <div class="product-info">
              <h3>{{ product.name }}</h3>
              <p>{{ product.description }}</p>
            </div>
          </el-card>
        </el-col>
      </el-row>
    </div>

    <!-- 技术解决方案 -->
    <div class="solutions-section">
      <h2>技术解决方案</h2>
      <el-row :gutter="30">
        <el-col :span="12" v-for="(solution, index) in solutions" :key="index">
          <div class="solution-item">
            <el-icon class="solution-icon">
              <component :is="solution.icon"></component>
            </el-icon>
            <div class="solution-content">
              <h3>{{ solution.title }}</h3>
              <p>{{ solution.description }}</p>
            </div>
          </div>
        </el-col>
      </el-row>
    </div>

    <!-- 服务优势 -->
    <div class="advantages-section">
      <h2>服务优势</h2>
      <el-row :gutter="30">
        <el-col :span="6" v-for="(advantage, index) in advantages" :key="index">
          <div class="advantage-item">
            <el-icon class="advantage-icon">
              <component :is="advantage.icon"></component>
            </el-icon>
            <h3>{{ advantage.title }}</h3>
            <p>{{ advantage.description }}</p>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import {
  Monitor,
  Connection,
  DataAnalysis,
  Setting,
  Lock,
  Service,
  Timer,
  User
} from '@element-plus/icons-vue'

const products = ref([
  {
    name: '智能数据分析平台',
    description: '基于AI技术的数据分析平台，帮助企业实现数据驱动决策',
    image: '/src/assets/products/data-analysis.jpg'
  },
  {
    name: '企业云服务解决方案',
    description: '安全可靠的云计算服务，助力企业数字化转型',
    image: '/src/assets/products/cloud-service.jpg'
  },
  {
    name: '智能物联网系统',
    description: '全方位的物联网解决方案，实现设备智能化管理',
    image: '/src/assets/products/iot.jpg'
  }
])

const solutions = ref([
  {
    title: '数字化转型',
    description: '为企业提供全方位的数字化转型解决方案，包括业务流程优化、数据治理等',
    icon: 'Monitor'
  },
  {
    title: '云原生架构',
    description: '基于云原生技术，提供高可用、可扩展的系统架构设计',
    icon: 'Connection'
  },
  {
    title: '大数据分析',
    description: '利用先进的大数据技术，挖掘数据价值，提供决策支持',
    icon: 'DataAnalysis'
  },
  {
    title: '系统集成',
    description: '提供专业的系统集成服务，确保各系统间无缝协作',
    icon: 'Setting'
  }
])

const advantages = ref([
  {
    title: '专业技术团队',
    description: '拥有经验丰富的技术专家团队',
    icon: 'User'
  },
  {
    title: '安全可靠',
    description: '采用先进的安全技术，保障数据安全',
    icon: 'Lock'
  },
  {
    title: '7*24小时服务',
    description: '全天候技术支持服务',
    icon: 'Service'
  },
  {
    title: '快速响应',
    description: '及时响应客户需求，提供高效解决方案',
    icon: 'Timer'
  }
])
</script>

<style scoped>
.products-container {
  padding: 20px 0;
}

.products-header {
  text-align: center;
  margin-bottom: 40px;
}

.products-header h1 {
  font-size: 36px;
  color: #303133;
  margin-bottom: 10px;
}

.subtitle {
  font-size: 18px;
  color: #909399;
}

.products-section,
.solutions-section,
.advantages-section {
  margin-bottom: 60px;
}

h2 {
  font-size: 28px;
  color: #303133;
  margin-bottom: 30px;
  text-align: center;
}

.product-card {
  margin-bottom: 30px;
  transition: transform 0.3s;
}

.product-card:hover {
  transform: translateY(-5px);
}

.product-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.product-info {
  padding: 20px;
}

.product-info h3 {
  font-size: 20px;
  color: #303133;
  margin-bottom: 10px;
}

.product-info p {
  color: #606266;
  line-height: 1.6;
}

.solution-item {
  display: flex;
  align-items: flex-start;
  padding: 20px;
  background: #f5f7fa;
  border-radius: 8px;
  margin-bottom: 20px;
}

.solution-icon {
  font-size: 24px;
  color: #409EFF;
  margin-right: 15px;
  margin-top: 5px;
}

.solution-content h3 {
  font-size: 18px;
  color: #303133;
  margin-bottom: 10px;
}

.solution-content p {
  color: #606266;
  line-height: 1.6;
}

.advantage-item {
  text-align: center;
  padding: 20px;
  background: #f5f7fa;
  border-radius: 8px;
  height: 100%;
}

.advantage-icon {
  font-size: 36px;
  color: #409EFF;
  margin-bottom: 15px;
}

.advantage-item h3 {
  font-size: 18px;
  color: #303133;
  margin-bottom: 10px;
}

.advantage-item p {
  color: #606266;
  line-height: 1.6;
}

@media screen and (max-width: 768px) {
  .el-col {
    width: 100%;
  }
  
  .products-header h1 {
    font-size: 28px;
  }
  
  .subtitle {
    font-size: 16px;
  }
}
</style> 