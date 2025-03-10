<template>
  <div class="section basic-info">
    <div class="profile-header">
      <el-avatar :size="100" :src="data.avatar" class="avatar" />
      <div class="name-title">
        <h1 class="name">{{ data.name }}</h1>
        <h2 class="title">{{ data.title }}</h2>
      </div>
    </div>
    
    <div class="contact-info">
      <div class="contact-item">
        <el-icon><Message /></el-icon>
        <span>{{ data.email }}</span>
      </div>
      <div class="contact-item">
        <el-icon><Phone /></el-icon>
        <span>{{ data.phone }}</span>
      </div>
      <div class="contact-item">
        <el-icon><Location /></el-icon>
        <span>{{ data.location }}</span>
      </div>
      <div class="contact-item" v-if="data.github">
        <el-icon><Link /></el-icon>
        <a :href="data.github" target="_blank">GitHub</a>
      </div>
      <div class="contact-item" v-if="data.website">
        <el-icon><Link /></el-icon>
        <a :href="data.website" target="_blank">个人网站</a>
      </div>
    </div>
    
    <div class="summary">
      <p>{{ data.summary }}</p>
    </div>
  </div>
</template>

<script setup>
import { ElAvatar, ElIcon } from 'element-plus'
import { Message, Phone, Location, Link } from '@element-plus/icons-vue'

defineProps({
  data: {
    type: Object,
    required: true
  }
})
</script>

<style scoped lang="scss">
.basic-info {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.profile-header {
  display: flex;
  align-items: center;
  gap: 30px;
}

.avatar {
  border: 3px solid var(--primary-color);
}

.name {
  font-size: 32px;
  color: var(--secondary-color);
  margin-bottom: 5px;
}

.title {
  font-size: 18px;
  color: var(--primary-color);
  font-weight: 500;
}

.contact-info {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 5px;
  
  a {
    color: var(--primary-color);
    text-decoration: none;
    
    &:hover {
      text-decoration: underline;
    }
  }
}

.summary {
  font-size: 16px;
  line-height: 1.8;
}
</style> 