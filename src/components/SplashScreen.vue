<script setup lang="ts">
import { ref } from 'vue';

const handleButtonClick = (action: string) => {
  console.log(`Clicked: ${action}`);
  // Ici, vous pouvez ajouter la logique pour rediriger ou effectuer une action
};
</script>

<template>
  <div class="splash-screen">
    <h1 class="title">Univers Ludique</h1>
    <div class="button-group">
      <button @click="handleButtonClick('Action ou Vérité')" class="btn btn-primary">
        <span class="btn-content">
          <span class="icon">🎲</span>
          <span class="text">Action ou Vérité</span>
        </span>
      </button>
      <button @click="handleButtonClick('Je n\'ai jamais')" class="btn btn-secondary">
        <span class="btn-content">
          <span class="icon">🍻</span>
          <span class="text">Je n'ai jamais</span>
        </span>
      </button>
    </div>
  </div>
</template>

<style scoped>
.splash-screen {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #1e3a8a 0%, #3730a3 100%);
  overflow: hidden;
}

.title {
  font-size: 3rem;
  margin-bottom: 3rem;
  text-align: center;
  color: #f0f9ff;
  text-shadow: 0 0 15px rgba(240, 249, 255, 0.7);
  animation: fadeInDown 1s ease-out;
}

.button-group {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  max-width: 600px;
}

.btn {
  padding: 0;
  font-size: 1.1rem;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 1px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
  overflow: hidden;
  position: relative;
}

.btn-content {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1rem 2rem;
  transition: all 0.3s ease;
}

.icon {
  margin-right: 10px;
  font-size: 1.2rem;
  transition: all 0.3s ease;
}

.btn:nth-child(1) {
  animation-delay: 0.5s;
}

.btn:nth-child(2) {
  animation-delay: 0.7s;
}

.btn:hover {
  transform: translateY(-3px) scale(1.05);
  box-shadow: 0 6px 8px rgba(0, 0, 0, 0.15);
}

.btn:hover .btn-content {
  transform: translateY(-100%);
}

.btn:hover::after {
  transform: translateY(0);
}

.btn::after {
  content: attr(data-hover);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  transform: translateY(100%);
  transition: transform 0.3s ease;
}

.btn-primary {
  background-color: #60a5fa;
  color: #1e3a8a;
}

.btn-primary::after {
  content: "Jouer !";
  background-color: #3b82f6;
  color: #ffffff;
}

.btn-secondary {
  background-color: #818cf8;
  color: #1e3a8a;
}

.btn-secondary::after {
  content: "Découvrir !";
  background-color: #6366f1;
  color: #ffffff;
}

@keyframes fadeInDown {
  from {
    opacity: 0;
    transform: translateY(-50px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 600px) {
  .title {
    font-size: 2.5rem;
  }

  .button-group {
    flex-direction: column;
    align-items: center;
  }

  .btn {
    width: 80%;
  }
}
</style>