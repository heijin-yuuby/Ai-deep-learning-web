<template>
  <div class="platforms-page llm-pages">
    <Navigation />
    
    <div class="page-header">   
      <div class="container">
        <h1 class="page-title">LLM Platforms Navigation</h1>
        <p class="page-subtitle">探索和访问各种强大的 AI 语言模型平台</p>
      </div>
    </div>
    
    <br>
    <div class="container main-content">
      <div class="intro-section">
        <div class="intro-content">
          <h2>体验各大LLM</h2>
          <p>时下的，先进的，你需要知道的LLM平台</p>
        </div>
      </div>
      
      <div>
        <LLMPlatforms ref="llmPlatformsRef" />
      </div>
      
      <br>
      <div class="container main-content">
        <div class="intro-section">
          <div class="intro-content">
            <h2>如果你想了解AI开发...</h2>
            <p>我们有相关的集成平台</p>
          </div>
        </div>
        <div>
          <LLMintegrationplatform ref="integrationPlatformsRef" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Navigation from '../components/layout/Navigation.vue';
import LLMPlatforms from '../components/Platforms/LLMPlatforms.vue';
import LLMintegrationplatform from '../components/Platforms/LLMintegrationplatform.vue';
import '../assets/styles/platforms.css';
import { ref, onMounted } from 'vue';

// 引用平台组件
const llmPlatformsRef = ref(null);
const integrationPlatformsRef = ref(null);

onMounted(() => {
  // 确保页面加载后立即隐藏所有卡片
  document.querySelectorAll('.platform-card').forEach(card => {
    card.style.opacity = '0';
  });
  
  // 给页面充分时间加载所有元素
  setTimeout(() => {
    setupPlatformCards('llm');
    setupPlatformCards('integration');
  }, 300); // 增加延迟确保页面完全加载
});

// 设置平台卡片的初始状态和动画
function setupPlatformCards(platformType) {
  // 选择对应的平台卡片
  const cards = platformType === 'llm' 
    ? document.querySelectorAll('.llm-platforms:first-of-type .platform-card')
    : document.querySelectorAll('.llm-platforms:last-of-type .platform-card');
  
  // 添加初始状态类
  cards.forEach(card => {
    // 移除可能的内联样式
    card.style.opacity = '';
    card.classList.add('platform-card-ready');
  });
  
  // 为初始视图中已经可见的卡片手动触发动画
  const triggerInitialAnimation = () => {
    // 为每个卡片添加动画，从左到右优雅地错开执行
    cards.forEach((card, index) => {
      setTimeout(() => {
        card.classList.remove('platform-card-ready');
        card.classList.add('platform-card-active');
      }, 200 * index); // 间隔时间
    });
  };
  
  // 立即为可视区域内的卡片触发动画
  triggerInitialAnimation();
  
  // 创建 Intersection Observer 用于处理滚动时进入视图的元素
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      // 仅处理进入视图的元素
      if (entry.isIntersecting) {
        // 停止观察，避免重复触发
        observer.unobserve(entry.target);
      }
    });
  }, {
    threshold: 0.2,
    rootMargin: '0px 0px -50px 0px'
  });

  // 观察相应的平台组件
  const targetRef = platformType === 'llm' ? llmPlatformsRef : integrationPlatformsRef;
  if (targetRef.value && targetRef.value.$el) {
    observer.observe(targetRef.value.$el);
  }
}
</script>

<style scoped>
/* 页面特定样式 */
.page-title {
  font-size: clamp(2rem, 6vw, 3rem);
  margin-bottom: 1rem;
  color: var(--text-light);
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  animation: fadeIn 1s ease-in-out;
}

.page-subtitle {
  font-size: clamp(0.9rem, 3vw, 1.2rem);
  max-width: 600px;
  margin: 0 auto;
  color: var(--text-light);
  padding: 0 20px;
  animation: fadeIn 1.5s ease-in-out;
}

.intro-section {
  margin-bottom: 30px;
  animation: float-up 1s ease-in-out;
}

.intro-content h2 {
  font-size: 1.8rem;
  margin-bottom: 10px;
  color: var(--primary-color);
  animation: fadeIn 1s ease-in-out;
}

.intro-content p {
  color: var(--text-secondary);
  animation: fadeIn 1.5s ease-in-out;
}
</style> 