<template>
  <div class="section">
    <h2 class="section-title">专业技能</h2>
    <div class="skills-container">
      <div v-for="skill in skills" :key="skill.name" class="skill-item">
        <div class="skill-header">
          <span class="skill-name">{{ skill.name }}</span>
          <span class="skill-level">{{ skill.level }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  skills: {
    type: Array,
    required: true
  }
})
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
  align-items: center;
}

.skill-name {
  font-weight: 500;
}

.skill-level {
  color: var(--primary-color);
}
</style>