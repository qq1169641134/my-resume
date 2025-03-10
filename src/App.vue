<template>
  <div class="container">
    <div id="resume" class="resume-container">
      <BasicInfo :data="resumeData.basicInfo" />
      <Skills :skills="resumeData.skills" />
      <Education :education="resumeData.education" />
      <WorkExperience :experiences="resumeData.workExperience" />
      <Projects :projects="resumeData.projects" />
    </div>

    <el-button
      type="primary"
      class="print-btn"
      @click="exportPDF"
      :icon="Download"
      size="large"
      round
    >
      导出PDF
    </el-button>
  </div>
</template>

<script setup>
import { ElButton } from "element-plus";
import { ref, onMounted, defineAsyncComponent } from "vue";
import { Download, House } from "@element-plus/icons-vue";
import BasicInfo from "./components/BasicInfo.vue";
import Skills from "./components/Skills.vue";
import Education from "./components/Education.vue";
import WorkExperience from "./components/WorkExperience.vue";
import Projects from "./components/Projects.vue";
// 使用导入的数据
const resumeData = ref(null);

// 在客户端环境中，尝试使用window上的数据（如果有的话）
if (typeof window !== "undefined" && window.resumeData) {
  resumeData.value = window.resumeData;
}

// 动态导入非核心组件
const html2pdf = () => import("html2pdf.js").then((m) => m.default || m);

// PDF导出功能
const exportPDF = async () => {
  const element = document.getElementById("resume");
  const html2pdfLib = await html2pdf();

  const opt = {
    margin: 10,
    filename: "张铨的个人简历.pdf",
    image: { type: "jpeg", quality: 0.98 },
    html2canvas: { scale: 2, useCORS: true },
    jsPDF: { unit: "mm", format: "a4", orientation: "portrait" },
  };

  html2pdfLib().set(opt).from(element).save();
};
</script>

<style scoped>
.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;
  position: relative;
}

.resume-container {
  background-color: white;
  padding: 30px;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  margin-bottom: 20px;
}

.print-btn {
  position: fixed;
  bottom: 30px;
  right: 30px;
  z-index: 100;
}
</style>
