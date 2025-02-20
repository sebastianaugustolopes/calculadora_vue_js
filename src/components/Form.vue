<script setup>
defineProps({
  getnumber1: {
    type: Function,
    required: true,
  },
  getnumber2: {
    type: Function,
    required: true,
  },
  getOperation: {
    type: Function,
    required: true,
  },
  Answer: {
    type: Number,
    required: true,
  },
});
</script>

<template>
  <div class="calculator-card">
    <header class="card-header">
      <div class="icon-container">
        <div class="calculator-icon">±×÷</div>
      </div>
      <h1 class="title">Calculadora Aritmética</h1>
      <p class="subtitle">Realize cálculos simples rapidamente</p>
    </header>

    <form class="calculator-form">
      <div class="input-group">
        <input
          required
          type="number"
          class="form-control"
          @keyup="(evento) => $props.getnumber1(evento)"
          placeholder="Primeiro número"
        />

        <select 
          class="operation-select" 
          @change="(evento) => $props.getOperation(evento)"
        >
          <option value="sum">+</option>
          <option value="subtract">-</option>
          <option value="multiply">×</option>
          <option value="divide">÷</option>
        </select>

        <input
          required
          type="number"
          class="form-control"
          @keyup="(evento) => $props.getnumber2(evento)"
          placeholder="Segundo número"
        />
      </div>
    </form>
    <div class="result-container">
      <h2 class="result-title">Resultado</h2>
      <span class="result-value">{{ Answer }}</span>
    </div>
  </div>
</template>

<style scoped>
.calculator-card {
  width: 100%;
  max-width: 40rem;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(8px);
  border-radius: 1.5rem;
  padding: 2.5rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.card-header {
  text-align: center;
  margin-bottom: 2.5rem;
}

.icon-container {
  display: flex;
  justify-content: center;
  margin-bottom: 1.5rem;
}

.calculator-icon {
  height: 4rem;
  width: 4rem;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  font-weight: bold;
  color: #60a5fa;
}

.title {
  font-size: 2rem;
  font-weight: bold;
  color: white;
  margin-bottom: 0.75rem;
}

.subtitle {
  color: #d1d5db;
  font-size: 1rem;
}

.calculator-form {
  width: 100%;
}

.input-group {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-control {
  width: 100%;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid #4b5563;
  border-radius: 0.75rem;
  color: white;
  font-size: 1.25rem;
  transition: all 0.3s ease;
}

.form-control::placeholder {
  color: #9ca3af;
}

.form-control:focus {
  outline: none;
  border-color: #60a5fa;
  box-shadow: 0 0 0 3px rgba(96, 165, 250, 0.2);
}

.operation-select {
  width: 100%;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid #4b5563;
  border-radius: 0.75rem;
  color: white;
  font-size: 1.5rem;
  text-align: center;
  cursor: pointer;
  transition: all 0.3s ease;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
}

.operation-select:focus {
  outline: none;
  border-color: #60a5fa;
  box-shadow: 0 0 0 3px rgba(96, 165, 250, 0.2);
}

.operation-select option {
  background: #1a1a1a;
  color: white;
}

.result-container {
  margin-top: 2.5rem;
  text-align: center;
}

.result-title {
  font-size: 1.5rem;
  font-weight: bold;
  color: white;
  margin-bottom: 1rem;
}

.result-value {
  font-size: 2rem;
  font-weight: bold;
  color: #60a5fa;
}

@media (max-width: 768px) {
  .calculator-card {
    padding: 2rem;
  }

  .title {
    font-size: 1.75rem;
  }

  .subtitle {
    font-size: 0.875rem;
  }

  .form-control, .operation-select {
    font-size: 1rem;
  }

  .result-title {
    font-size: 1.25rem;
  }

  .result-value {
    font-size: 1.75rem;
  }
}
</style>