<template>
  <div class="section">
    <h2 class="section-title">工作经历</h2>
    <div class="experience-list">
      <div class="experience-item" v-for="(exp, index) in experiences" :key="index">
        <div class="experience-header">
          <h3 class="company">{{ exp.company }}</h3>
          <span class="date">{{ exp.date }}</span>
        </div>
        <div class="position">{{ exp.position }}</div>
        <ul class="responsibilities">
          <li v-for="(item, idx) in exp.responsibilities" :key="idx">
            {{ item }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ElTimeline, ElTimelineItem } from 'element-plus'

defineProps({
  experiences: {
    type: Array,
    required: true
  }
})
</script>

<style scoped lang="scss">
.experience-list {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.experience-item {
  position: relative;
  border-left: 3px solid var(--primary-color);
  padding: 0 0 0 20px;
}

.experience-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 5px;
}

.company {
  font-size: 18px;
  font-weight: 600;
  color: var(--secondary-color);
}

.date {
  color: #666;
  font-size: 14px;
}

.position {
  font-weight: 500;
  margin-bottom: 10px;
  color: var(--primary-color);
  font-size: 16px;
}

.responsibilities {
  list-style-position: inside;
  color: #555;
  
  li {
    margin-bottom: 5px;
    line-height: 1.6;
  }
}
</style> 