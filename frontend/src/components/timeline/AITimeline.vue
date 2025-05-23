<template>
  <div class="timeline-container">
    <div class="timeline-header">
      <h2>人工智能技术发展史</h2>
    </div>
    
    <div class="timeline">
      <div 
        v-for="(period, index) in timelinePeriods" 
        :key="index"
        class="timeline-item"
        :class="{ 'left': index % 2 === 0, 'right': index % 2 === 1 }"
      >
        <div class="timeline-dot"></div>
        
        <div class="timeline-period">
          <h3>{{ period.title }}</h3>
          <div class="timeline-year">{{ period.years }}</div>
        </div>
        
        <div 
          class="timeline-content"
          @mouseenter="activePeriod = period.id"
          @mouseleave="activePeriod = null"
          :class="{ 'active': activePeriod === period.id }"
        >
          <div class="timeline-content-inner" v-html="period.content"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const activePeriod = ref(null);

const timelinePeriods = [
  {
    id: 'early',
    title: '早期理论萌芽',
    years: '20世纪40-50年代',
    content: `
      <p>1943年，沃伦・麦卡洛克（Warren McCulloch）和沃尔特・皮茨（Walter Pitts）提出了人工神经元模型，这一理论为神经网络的发展奠定了基础，开启了模拟人类大脑神经元工作方式的探索。</p>
      <p>1950年，阿兰・图灵（Alan Turing）发表了《计算机器与智能》论文，提出了图灵测试，为判断机器是否具有智能提供了一个开创性的标准，引发了人们对于机器智能的广泛思考与讨论。</p>
      <p>1956年，达特茅斯会议召开，约翰・麦卡锡（John McCarthy）、马文・明斯基（Marvin Minsky）等科学家聚在一起，首次提出"人工智能"这一术语，标志着人工智能作为一门独立学科正式诞生，众多早期的人工智能研究思路和方法在这次会议中被提出和探讨。</p>
    `
  },
  {
    id: 'development',
    title: '发展起伏期',
    years: '20世纪60-80年代',
    content: `
      <p>在20世纪60年代，基于逻辑推理的方法在人工智能领域占据主导。科学家们试图通过编写大量规则让计算机进行逻辑推理，解决问题，如自动定理证明等。然而，由于计算能力的限制以及对问题复杂性估计不足，很多项目进展缓慢，遭遇瓶颈，人工智能发展进入低谷。</p>
      <p>到了70年代，专家系统崭露头角，如MYCIN系统，它能够根据患者症状、病史等信息诊断细菌感染疾病并推荐治疗方案，将特定领域的专家知识编码到计算机程序中，使得人工智能在实际应用中取得一定成果，推动了人工智能从理论研究走向实际应用。</p>
      <p>80年代，神经网络迎来复兴，多层感知机（MLP）的反向传播算法被重新发现，解决了早期神经网络训练中的关键难题，使得神经网络能够处理更复杂的任务，如语音识别和图像识别，引发了新一轮的研究热潮。同时，日本提出第五代计算机计划，目标是研制具有人工智能的计算机，推动了知识工程和自然语言处理等领域的研究。</p>
    `
  },
  {
    id: 'modern',
    title: '现代人工智能崛起',
    years: '20世纪90年代-21世纪初',
    content: `
      <p>随着计算机性能的大幅提升和互联网的普及，机器学习成为人工智能的核心发展方向。决策树、支持向量机等多种机器学习算法得到广泛研究和应用，它们能够从大量数据中自动学习模式和规律，在数据挖掘、信息检索等领域发挥重要作用。</p>
      <p>在自然语言处理方面，统计语言模型的出现改变了传统基于规则的处理方式，通过对大规模文本数据的统计分析来处理语言问题，显著提高了机器翻译、语音识别等任务的准确性。</p>
      <p>90年代末，强化学习也取得重要进展，其让智能体通过与环境进行交互并根据奖励反馈来学习最优行为策略，为解决机器人控制、游戏等领域的问题提供了新途径。</p>
    `
  },
  {
    id: 'deep-learning',
    title: '深度学习引领的爆发期',
    years: '2010年至今',
    content: `
      <p>2012年，深度学习在图像识别领域取得重大突破，Hinton团队的AlexNet在ImageNet图像识别大赛中以巨大优势夺冠，其通过构建深层神经网络，能够自动从海量图像数据中学习到高级特征，开启了深度学习在人工智能领域的统治时代。</p>
      <p>随后，深度学习在语音识别、自然语言处理等众多领域全面开花。循环神经网络（RNN）及其变体长短时记忆网络（LSTM）在处理序列数据方面表现出色，极大提升了语音识别和机器翻译的性能。</p>
      <p>2017年，谷歌提出Transformer架构，摒弃了传统的循环和卷积结构，引入注意力机制，使得模型能够更好地捕捉文本中的长距离依赖关系，在自然语言处理任务中取得革命性成果。</p>
      <p>基于Transformer架构的GPT系列和BERT模型相继问世，前者在文本生成等任务中展现出强大能力，后者则在自然语言理解任务中表现卓越，推动人工智能技术在实际应用中达到新高度，如智能客服、智能写作、智能翻译等应用广泛普及，深刻改变人们的生活和工作方式。</p>
    `
  }
];
</script>

<style scoped>
.timeline-container {
  position: relative;
  padding: 2rem 0;
  max-width: 1200px;
  margin: 0 auto;
}

.timeline-header {
  text-align: center;
  margin-bottom: 60px;
}

.timeline-header h2 {
  font-size: 2rem;
  color: var(--primary-color);
}

.timeline-line {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 4px;
  height: 100%;
  background: var(--primary-gradient);
  border-radius: 2px;
}

.timeline-item {
  position: relative;
  margin-bottom: 4rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.timeline-item.timeline-item-ready {
  opacity: 0;
  transform: translateY(20px);
}

.timeline-item.timeline-item-active {
  opacity: 1;
  transform: translateY(0);
}

.timeline-item:nth-child(odd) {
  flex-direction: row;
}

.timeline-item:nth-child(even) {
  flex-direction: row-reverse;
}

.timeline-dot {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 24px;
  height: 24px;
  background: var(--primary-gradient);
  border-radius: 50%;
  z-index: 2;
  box-shadow: 0 0 0 4px var(--bg-primary), 0 0 0 6px var(--accent-purple);
  transition: all var(--transition-normal);
}

.timeline-dot:hover {
  transform: translateX(-50%) scale(1.2);
  box-shadow: 0 0 0 4px var(--bg-primary), 0 0 0 8px var(--accent-purple);
}

.timeline-period {
  width: 45%;
  padding: 1.5rem;
  background: var(--card-bg);
  border-radius: 1rem;
  box-shadow: var(--shadow-md);
  border: 1px solid var(--card-border);
  transition: all var(--transition-normal);
}

.timeline-period:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-lg);
}

.timeline-period h3 {
  color: var(--text-primary);
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.timeline-year {
  font-size: 0.8rem;
  color: #666;
}

.timeline-content {
  width: 45%;
  padding: 1.5rem;
  background: var(--card-bg);
  border-radius: 1rem;
  box-shadow: var(--shadow-md);
  border: 1px solid var(--card-border);
  transition: all var(--transition-normal);
}

.timeline-content:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-lg);
}

.timeline-content h4 {
  color: var(--text-primary);
  font-size: 1.25rem;
  margin-bottom: 1rem;
  position: relative;
  padding-bottom: 0.5rem;
}

.timeline-content h4::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 50px;
  height: 3px;
  background: var(--primary-gradient);
  border-radius: 2px;
}

.timeline-content p {
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: 1rem;
}

.timeline-content ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.timeline-content li {
  color: var(--text-tertiary);
  margin-bottom: 0.5rem;
  padding-left: 1.5rem;
  position: relative;
}

.timeline-content li::before {
  content: '•';
  position: absolute;
  left: 0;
  color: var(--accent-purple);
}

@media (max-width: 768px) {
  .timeline-line {
    left: 20px;
  }

  .timeline-item {
    flex-direction: column !important;
    margin-left: 40px;
  }

  .timeline-dot {
    left: 20px;
  }

  .timeline-period,
  .timeline-content {
    width: 100%;
    margin-bottom: 1rem;
  }
}
</style> 