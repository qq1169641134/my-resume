<template>
  <div class="section projects-section">
    <h2 class="section-title">项目经验</h2>
    <div class="content">
      <div v-for="(project, index) in projects" :key="index" class="project-item">
        <div class="left-border"></div>
        <div class="project-content">
          <div class="project-header">
            <h3 class="project-name">{{ project.name }}</h3>
            <span class="project-date">{{ project.date }}</span>
          </div>
          <p class="project-description">{{ project.description }}</p>
          <div class="project-technologies">
            <span v-for="(tech, tIndex) in project.technologies" :key="tIndex" class="tech-tag">
              {{ tech }}
            </span>
          </div>
          <ul class="responsibilities-list">
            <li v-for="(item, rIndex) in project.responsibilities" :key="rIndex">
              {{ item }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ElTag } from 'element-plus'

defineProps({
  projects: {
    type: Array,
    default: () => []
  }
})
</script>

<style scoped lang="scss">
.projects-section {
  margin-bottom: 2rem;
  
  .section-title {
    border-bottom: 2px solid #3498db;
    padding-bottom: 0.5rem;
    margin-bottom: 1.5rem;
    color: #2c3e50;
    font-size: 1.5rem;
  }
  
  .content {
    display: flex;
    flex-direction: column;
    gap: 3rem;
  }
  
  .project-item {
    position: relative;
    display: flex;
    border-radius: 0;
    background: transparent;
    box-shadow: none;
    margin-bottom: 0;
    
    .left-border {
      width: 4px;
      background: #3498db;
      margin-right: 15px;
      border-radius: 2px;
    }
    
    .project-content {
      flex: 1;
      padding-bottom: 1rem;
    }
    
    .project-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.5rem;
      
      .project-name {
        font-size: 1.25rem;
        font-weight: 600;
        color: #2c3e50;
        margin: 0;
      }
      
      .project-date {
        color: #7f8c8d;
        font-size: 0.9rem;
      }
    }
    
    .project-description {
      margin-bottom: 0.75rem;
      color: #34495e;
      line-height: 1.5;
    }
    
    .project-technologies {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 1rem;
      
      .tech-tag {
        background-color: #ecf0f1;
        color: #2980b9;
        padding: 0.2rem 0.6rem;
        border-radius: 4px;
        font-size: 0.85rem;
      }
    }
    
    .responsibilities-list {
      padding-left: 1.2rem;
      margin: 0;
      
      li {
        margin-bottom: 0.5rem;
        color: #34495e;
        line-height: 1.5;
        
        &:last-child {
          margin-bottom: 0;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .project-item {
    .project-header {
      flex-direction: column;
      align-items: flex-start;
      
      .project-date {
        margin-top: 0.25rem;
      }
    }
    
    .project-technologies {
      .tech-tag {
        font-size: 0.75rem;
      }
    }
  }
}
</style> 