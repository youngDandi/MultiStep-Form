<script setup>
import { ref } from 'vue';
import SideDiv from './components/SideDiv.vue';
import StepOne from './components/StepOne.vue';
import StepTwo from './components/StepTwo.vue';
import StepThree from './components/StepThree.vue';

// Estado para controlar a etapa atual
const currentStep = ref(1);

// Função para avançar para a próxima etapa
const nextStep = () => {
  if (currentStep.value < 3) {
    currentStep.value += 1;
  }
};

// Função para voltar à etapa anterior
const previousStep = () => {
  if (currentStep.value > 1) {
    currentStep.value -= 1;
  }
};

// Computed para determinar o progresso e o texto do progresso
const progressPercentage = () => {
  return (currentStep.value / 3) * 100;
};

const progressText = () => {
  return `${currentStep.value} OF 3 COMPLETED`;
};
</script>

<template>
  <div class="mainWindow">
    <SideDiv />
    <div>
      <p>{{ progressText() }}</p>
      <input type="range" id="range" :value="progressPercentage()" disabled>

      <!-- Renderiza o componente de acordo com a etapa atual -->
      <StepOne v-if="currentStep === 1" @next-step="nextStep" />
      <StepTwo v-else-if="currentStep === 2" @next-step="nextStep" @previous-step="previousStep" />
      <StepThree v-else-if="currentStep === 3 " @previous-step="previousStep"/>
    </div>
  </div>
</template>

<style scoped>


.mainWindow {
  display: flex;
  flex-direction: row;
  width: 100vw;
  height: 100vh;
  position: relative;
  min-height: 100vh;
}

#range {
  width: 70%;
}

input[type="range"] {
  -webkit-appearance: none;
  appearance: none;
  width: 100%;
  height: 8px;
  background: #01b681;
  outline: none;
  border-radius: 5px;
  transition: background 0.3s;
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 0; /* Define a largura da "bolinha" como zero para ocultá-la */
  height: 0; /* Define a altura como zero */
}

input[type="range"]::-moz-range-thumb {
  width: 0;
  height: 0;
}
</style>
