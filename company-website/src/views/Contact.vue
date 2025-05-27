<template>
  <div class="contact">
    <h2 class="section-title">联系我们</h2>
    
    <el-row :gutter="40">
      <!-- 联系信息 -->
      <el-col :span="12">
        <div class="contact-info">
          <h3>联系方式</h3>
          <el-descriptions :column="1" border>
            <el-descriptions-item label="公司地址">
              <el-icon><Location /></el-icon>
              北京市朝阳区科技园区88号创新大厦A座15层
            </el-descriptions-item>
            <el-descriptions-item label="联系电话">
              <el-icon><Phone /></el-icon>
              400-888-8888（总机）
              <br>
              010-88888888（北京）
            </el-descriptions-item>
            <el-descriptions-item label="电子邮箱">
              <el-icon><Message /></el-icon>
              contact@company.com（商务合作）
              <br>
              support@company.com（技术支持）
            </el-descriptions-item>
            <el-descriptions-item label="工作时间">
              <el-icon><Timer /></el-icon>
              周一至周五 9:00-18:00
              <br>
              技术支持 7*24小时
            </el-descriptions-item>
          </el-descriptions>

          <div class="social-media">
            <h3>关注我们</h3>
            <div class="social-icons">
              <el-button circle>
                <el-icon><Share /></el-icon>
              </el-button>
              <el-button circle>
                <el-icon><ChatDotRound /></el-icon>
              </el-button>
              <el-button circle>
                <el-icon><Position /></el-icon>
              </el-button>
            </div>
          </div>
        </div>
      </el-col>

      <!-- 在线留言 -->
      <el-col :span="12">
        <div class="message-form">
          <h3>在线留言</h3>
          <el-form
            ref="formRef"
            :model="form"
            :rules="rules"
            label-width="80px"
          >
            <el-form-item label="姓名" prop="name">
              <el-input v-model="form.name" placeholder="请输入您的姓名" />
            </el-form-item>
            <el-form-item label="电话" prop="phone">
              <el-input v-model="form.phone" placeholder="请输入您的联系电话" />
            </el-form-item>
            <el-form-item label="邮箱" prop="email">
              <el-input v-model="form.email" placeholder="请输入您的电子邮箱" />
            </el-form-item>
            <el-form-item label="留言内容" prop="message">
              <el-input
                v-model="form.message"
                type="textarea"
                :rows="4"
                placeholder="请输入您的留言内容"
              />
            </el-form-item>
            <el-form-item>
              <el-button type="primary" @click="submitForm(formRef)">提交留言</el-button>
            </el-form-item>
          </el-form>
        </div>
      </el-col>
    </el-row>

    <!-- 公司地图 -->
    <div class="map-section">
      <h3>公司位置</h3>
      <div class="map-container">
        <!-- 这里可以集成实际的地图组件，如高德地图、百度地图等 -->
        <img src="https://images.unsplash.com/photo-1526772662000-3f88f10405ff?w=1200&h=400&fit=crop" alt="公司地图" class="map-image">
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { ElMessage } from 'element-plus'

const formRef = ref(null)
const form = ref({
  name: '',
  phone: '',
  email: '',
  message: ''
})

const rules = {
  name: [
    { required: true, message: '请输入姓名', trigger: 'blur' },
    { min: 2, max: 20, message: '长度在 2 到 20 个字符', trigger: 'blur' }
  ],
  phone: [
    { required: true, message: '请输入联系电话', trigger: 'blur' },
    { pattern: /^1[3-9]\d{9}$/, message: '请输入正确的手机号码', trigger: 'blur' }
  ],
  email: [
    { required: true, message: '请输入邮箱地址', trigger: 'blur' },
    { type: 'email', message: '请输入正确的邮箱地址', trigger: 'blur' }
  ],
  message: [
    { required: true, message: '请输入留言内容', trigger: 'blur' },
    { min: 10, max: 500, message: '长度在 10 到 500 个字符', trigger: 'blur' }
  ]
}

const submitForm = async (formEl) => {
  if (!formEl) return
  await formEl.validate((valid, fields) => {
    if (valid) {
      // 这里可以添加实际的表单提交逻辑
      ElMessage.success('留言提交成功！')
      form.value = {
        name: '',
        phone: '',
        email: '',
        message: ''
      }
    } else {
      console.log('error submit!', fields)
    }
  })
}
</script>

<style scoped>
.contact {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.section-title {
  text-align: center;
  margin-bottom: 40px;
  color: #303133;
}

.contact-info {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.message-form {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.social-media {
  margin-top: 30px;
}

.social-icons {
  display: flex;
  gap: 10px;
  margin-top: 15px;
}

.map-section {
  margin-top: 40px;
}

.map-container {
  margin-top: 20px;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.map-image {
  width: 100%;
  height: 400px;
  object-fit: cover;
}

h3 {
  color: #303133;
  margin-bottom: 20px;
}

:deep(.el-descriptions-item__label) {
  width: 100px;
}

:deep(.el-icon) {
  margin-right: 8px;
  vertical-align: middle;
}
</style> 