<template>
  <div class="about">
    <!-- 公司历史时间线 -->
    <div class="history-section">
      <h2 class="section-title">发展历程</h2>
      <el-timeline>
        <el-timeline-item
          v-for="(history, index) in companyHistory"
          :key="index"
          :timestamp="history.year"
          placement="top"
        >
          <el-card>
            <h3>{{ history.title }}</h3>
            <p>{{ history.description }}</p>
          </el-card>
        </el-timeline-item>
      </el-timeline>
    </div>

    <!-- 企业文化 -->
    <div class="culture-section">
      <h2 class="section-title">企业文化</h2>
      <el-row :gutter="20">
        <el-col :span="8" v-for="(culture, index) in companyCulture" :key="index">
          <el-card class="culture-card">
            <el-icon class="culture-icon">
              <component :is="culture.icon"></component>
            </el-icon>
            <h3>{{ culture.title }}</h3>
            <p>{{ culture.description }}</p>
          </el-card>
        </el-col>
      </el-row>
    </div>
    
    <!-- 核心团队 -->
    <div class="team-section">
      <h2 class="section-title">核心团队</h2>
      <el-row :gutter="20">
        <el-col :span="6" v-for="(member, index) in teamMembers" :key="index">
          <el-card class="team-card">
            <img :src="member.avatar" :alt="member.name" class="member-avatar">
            <h3>{{ member.name }}</h3>
            <p class="member-position">{{ member.position }}</p>
            <p class="member-description">{{ member.description }}</p>
          </el-card>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const companyHistory = ref([
  {
    year: '2010',
    title: '公司成立',
    description: '公司在北京成立，开始专注于企业级软件解决方案的研发'
  },
  {
    year: '2013',
    title: '技术突破',
    description: '成功研发第一代企业管理系统，获得多项技术专利'
  },
  {
    year: '2015',
    title: '业务扩展',
    description: '成功拓展海外市场，在新加坡、日本设立分支机构，服务客户超过1000家'
  },
  {
    year: '2018',
    title: '战略升级',
    description: '完成B轮融资，估值超过10亿，开始布局人工智能和大数据领域'
  },
  {
    year: '2020',
    title: '技术创新',
    description: '发布新一代AI驱动的企业解决方案，获得行业广泛认可'
  },
  {
    year: '2023',
    title: '持续发展',
    description: '员工规模突破500人，年营收超过5亿，成为行业领军企业'
  }
])

const companyCulture = ref([
  {
    icon: 'Aim',
    title: '使命',
    description: '用科技创新推动行业发展，为客户创造更大价值，让科技改变世界'
  },
  {
    icon: 'View',
    title: '愿景',
    description: '成为全球领先的企业级软件服务提供商，引领行业发展方向'
  },
  {
    icon: 'Star',
    title: '价值观',
    description: '诚信为本、创新为魂、专业为基、共赢为道'
  }
])

const teamMembers = ref([
  {
    name: '张明',
    position: '首席执行官',
    description: '前微软高级技术专家，拥有20年行业经验，曾领导多个重大项目，获得多项技术专利',
    avatar: 'https://images.unsplash.com/photo-1560250097-0b93528c311a?w=150&h=150&fit=crop'
  },
  {
    name: '李华',
    position: '技术总监',
    description: '前谷歌技术专家，计算机科学博士，拥有15项技术专利，主导公司核心技术研发',
    avatar: 'https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?w=150&h=150&fit=crop'
  },
  {
    name: '王芳',
    position: '市场总监',
    description: '前IBM市场专家，MBA学位，擅长品牌战略规划，带领团队实现连续5年业绩翻倍',
    avatar: 'https://images.unsplash.com/photo-1580489944761-15a19d654956?w=150&h=150&fit=crop'
  },
  {
    name: '刘强',
    position: '运营总监',
    description: '前阿里巴巴运营专家，拥有丰富的互联网运营经验，注重效率和质量，推动公司运营体系升级',
    avatar: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=150&h=150&fit=crop'
  }
])
</script>

<style scoped>
.about {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.section-title {
  text-align: center;
  margin-bottom: 40px;
  color: #303133;
}

.history-section {
  margin-bottom: 60px;
}

.culture-section {
  margin-bottom: 60px;
}

.culture-card {
  text-align: center;
  padding: 20px;
  height: 100%;
  transition: transform 0.3s;
}

.culture-card:hover {
  transform: translateY(-5px);
}

.culture-icon {
  font-size: 40px;
  color: #409EFF;
  margin-bottom: 20px;
}

.team-section {
  margin-bottom: 40px;
}

.team-card {
  text-align: center;
  padding: 20px;
  height: 100%;
  transition: transform 0.3s;
}

.team-card:hover {
  transform: translateY(-5px);
}

.member-avatar {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  margin-bottom: 15px;
}

.member-position {
  color: #409EFF;
  margin: 10px 0;
}

.member-description {
  color: #606266;
  line-height: 1.6;
}
</style> 