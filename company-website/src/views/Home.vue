<template>
  <div class="home">
    <!-- 轮播图部分 -->
    <el-carousel :interval="5000" type="card" height="400px">
      <el-carousel-item v-for="item in carouselItems" :key="item.id">
        <img :src="item.image" :alt="item.title" class="carousel-image">
        <div class="carousel-content">
          <h2>{{ item.title }}</h2>
          <p>{{ item.description }}</p>
        </div>
      </el-carousel-item>
    </el-carousel>

    <!-- 公司简介部分 -->
    <div class="section company-intro">
      <h2 class="section-title">公司简介</h2>
      <div class="intro-content">
        <div class="intro-text">
          <p>智创未来科技有限公司成立于2020年，是一家专注于人工智能和智能制造领域的高新技术企业。我们致力于为客户提供创新的技术解决方案，推动产业数字化转型。</p>
          <p>公司拥有一支高素质的研发团队，在人工智能、大数据、云计算等领域具有丰富的经验和技术积累。我们始终坚持"创新驱动发展"的理念，不断探索前沿技术，为客户创造更大的价值。</p>
        </div>
        <div class="intro-image">
          <img src="https://images.unsplash.com/photo-1550751827-4bd374c3f58b" alt="公司简介">
        </div>
      </div>
    </div>

    <!-- 核心优势部分 -->
    <div class="section advantages">
      <h2 class="section-title">核心优势</h2>
      <el-row :gutter="30">
        <el-col :span="8" v-for="item in advantages" :key="item.id">
          <el-card class="advantage-card">
            <img :src="item.image" :alt="item.title" class="advantage-image">
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </el-card>
        </el-col>
      </el-row>
    </div>

    <!-- 新闻动态部分 -->
    <div class="section news">
      <h2 class="section-title">新闻动态</h2>
      <el-row :gutter="30">
        <el-col :span="8" v-for="item in news" :key="item.id">
          <el-card class="news-card" :body-style="{ padding: '0px' }">
            <img :src="item.image" class="news-image">
            <div class="news-content">
              <h3>{{ item.title }}</h3>
              <p class="news-date">{{ item.date }}</p>
              <p class="news-summary">{{ item.summary }}</p>
              <el-button type="primary" text>查看详情</el-button>
            </div>
          </el-card>
        </el-col>
      </el-row>
    </div>

    <!-- 合作伙伴部分 -->
    <div class="section partners">
      <h2 class="section-title">合作伙伴</h2>
      <div class="partners-grid">
        <div class="partner-item" v-for="item in partners" :key="item.id">
          <img :src="item.logo" :alt="item.name" class="partner-logo">
          <p class="partner-name">{{ item.name }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const carouselItems = ref([
  {
    id: 1,
    title: '智能科技 引领未来',
    description: '致力于人工智能技术创新，推动产业智能化升级',
    image: 'https://images.unsplash.com/photo-1550751827-4bd374c3f58b'
  },
  {
    id: 2,
    title: '智能制造 创新服务',
    description: '提供全方位的智能制造解决方案，助力企业数字化转型',
    image: 'https://images.unsplash.com/photo-1581094794329-c8112a89af12'
  },
  {
    id: 3,
    title: '专业团队 优质服务',
    description: '拥有经验丰富的技术团队，为客户提供专业的技术支持',
    image: 'https://images.unsplash.com/photo-1522202176988-66273c2fd55f'
  }
])

const advantages = ref([
  {
    id: 1,
    title: '技术创新',
    description: '拥有多项自主知识产权，在人工智能领域保持技术领先',
    image: 'https://images.unsplash.com/photo-1550751827-4bd374c3f58b'
  },
  {
    id: 2,
    title: '专业团队',
    description: '汇聚行业精英，打造专业的技术研发和服务团队',
    image: 'https://images.unsplash.com/photo-1522071820081-009f0129c71c'
  },
  {
    id: 3,
    title: '优质服务',
    description: '提供7*24小时技术支持，确保客户系统稳定运行',
    image: 'https://images.unsplash.com/photo-1573497620053-ea5300f94f21'
  }
])

const news = ref([
  {
    id: 1,
    title: '公司成功举办2024年技术创新大会',
    date: '2024-03-15',
    summary: '探讨人工智能最新发展趋势，分享技术创新成果',
    image: 'https://images.unsplash.com/photo-1540575467063-178a50c2df87'
  },
  {
    id: 2,
    title: '我司荣获"年度最具创新力企业"称号',
    date: '2024-02-28',
    summary: '凭借在人工智能领域的突出贡献，获得行业认可',
    image: 'https://images.unsplash.com/photo-1557804506-669a67965ba0'
  },
  {
    id: 3,
    title: '新一代AI产品发布会圆满举行',
    date: '2024-01-20',
    summary: '发布多款创新AI产品，引领行业发展方向',
    image: 'https://images.unsplash.com/photo-1556761175-b413da4baf72'
  }
])

const partners = ref([
  {
    id: 1,
    name: '华为技术',
    logo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Huawei_Logo.svg/2560px-Huawei_Logo.svg.png'
  },
  {
    id: 2,
    name: '阿里巴巴',
    logo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/Alibaba_Group_logo.svg/2560px-Alibaba_Group_logo.svg.png'
  },
  {
    id: 3,
    name: '腾讯科技',
    logo: 'https://www.tencent.com/img/index/tencent_logo.png'
  },
  {
    id: 4,
    name: '百度智能',
    logo: 'https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png'
  },
  {
    id: 5,
    name: '京东科技',
    logo: 'https://www.jd.com/favicon.ico'
  },
  {
    id: 6,
    name: '小米科技',
    logo: 'https://s02.mifile.cn/assets/static/image/logo-mi2.png'
  }
])
</script>

<style scoped>
.home {
  padding: 20px 0;
}

.section {
  padding: 60px 0;
}

.section-title {
  text-align: center;
  font-size: 32px;
  color: #303133;
  margin-bottom: 40px;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 3px;
  background-color: #409EFF;
}

/* 轮播图样式 */
.carousel-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.carousel-content {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 20px;
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.7));
  color: white;
}

.carousel-content h2 {
  margin: 0;
  font-size: 24px;
}

.carousel-content p {
  margin: 10px 0 0;
  font-size: 16px;
}

/* 公司简介样式 */
.intro-content {
  display: flex;
  align-items: center;
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.intro-text {
  flex: 1;
}

.intro-text p {
  margin: 0 0 20px;
  line-height: 1.8;
  color: #606266;
}

.intro-image {
  flex: 1;
}

.intro-image img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 8px;
}

/* 核心优势样式 */
.advantage-card {
  height: 100%;
  transition: transform 0.3s;
}

.advantage-card:hover {
  transform: translateY(-5px);
}

.advantage-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.advantage-card h3 {
  margin: 20px 0 10px;
  color: #303133;
}

.advantage-card p {
  color: #606266;
  line-height: 1.6;
}

/* 新闻动态样式 */
.news-card {
  height: 100%;
  transition: transform 0.3s;
}

.news-card:hover {
  transform: translateY(-5px);
}

.news-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.news-content {
  padding: 20px;
}

.news-content h3 {
  margin: 0 0 10px;
  font-size: 18px;
  color: #303133;
}

.news-date {
  color: #909399;
  font-size: 14px;
  margin-bottom: 10px;
}

.news-summary {
  color: #606266;
  line-height: 1.6;
  margin-bottom: 15px;
}

/* 合作伙伴样式 */
.partners-grid {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.partner-item {
  text-align: center;
  padding: 20px;
  background: white;
  border-radius: 8px;
  transition: transform 0.3s;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.partner-item:hover {
  transform: translateY(-5px);
}

.partner-logo {
  width: 120px;
  height: 60px;
  object-fit: contain;
  margin-bottom: 10px;
  opacity: 0.7;
  transition: all 0.3s ease;
  background-color: white;
  padding: 5px;
  border-radius: 4px;
  mix-blend-mode: multiply;
  filter: brightness(0.9);
}

.partner-item:hover .partner-logo {
  opacity: 1;
  transform: scale(1.05);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  filter: brightness(1);
}

.partner-name {
  color: #606266;
  margin: 0;
  font-size: 14px;
}

@media screen and (max-width: 768px) {
  .intro-content {
    flex-direction: column;
  }

  .partners-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style> 