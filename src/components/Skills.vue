<template>
  <div class="section">
    <h2 class="section-title">专业技能</h2>
    <div class="skills-container">
      <div v-for="skill in skills" :key="skill.name" class="skill-item">
        <div class="skill-header">
          <span class="skill-name">{{ skill.name }}</span>
          <span class="skill-level">{{ skill.level }}%</span>
        </div>
        <el-progress 
          :percentage="skill.level" 
          :show-text="false"
          :stroke-width="10"
          :color="getColorForLevel(skill.level)"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ElProgress } from 'element-plus'
const props = defineProps({
  skills: {
    type: Array,
    required: true
  }
})

const getColorForLevel = (level) => {
  if (level >= 90) return '#67c23a'
  if (level >= 75) return '#409eff'
  if (level >= 60) return '#e6a23c'
  return '#f56c6c'
}
</script>

<style scoped lang="scss">
.skills-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}

.skill-item {
  margin-bottom: 15px;
}

.skill-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 5px;
}

.skill-name {
  font-weight: 500;
}

.skill-level {
  color: var(--primary-color);
}
</style> 