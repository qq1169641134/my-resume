<template>
  <div class="section">
    <h2 class="section-title">教育背景</h2>
    <div class="education-list">
      <div class="education-item" v-for="(edu, index) in education" :key="index">
        <div class="education-header">
          <h3 class="school">{{ edu.school }}</h3>
          <span class="date">{{ edu.date }}</span>
        </div>
        <div class="degree">{{ edu.degree }}</div>
        <p class="description" v-if="edu.description">{{ edu.description }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  education: {
    type: Array,
    required: true
  }
})
</script>

<style scoped lang="scss">
.education-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.education-item {
  position: relative;
  padding-left: 20px;
  
  &::before {
    content: '';
    position: absolute;
    left: 0;
    top: 5px;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: var(--primary-color);
  }
}

.education-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 5px;
}

.school {
  font-size: 18px;
  font-weight: 600;
  color: var(--secondary-color);
}

.date {
  color: #666;
  font-size: 14px;
}

.degree {
  font-weight: 500;
  margin-bottom: 5px;
  color: var(--primary-color);
}

.description {
  color: #555;
  line-height: 1.6;
}
</style> 