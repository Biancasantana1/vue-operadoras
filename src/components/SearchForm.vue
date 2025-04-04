<template>
    <div class="form-group">
      <input
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
        @keydown.enter="$emit('search')"
        type="text"
        placeholder="Digite a razão social"
      />
      <button @click="$emit('search')">Buscar</button>
    </div>
  </template>
  
  <script>
  export default {
    name: "SearchForm",
    props: {
      modelValue: String
    }
  };
  </script>
  
  <style scoped>
  .form-group {
    display: flex;
    gap: 1rem;
    margin-bottom: 2rem;
  }
  
  input {
    flex: 1;
    padding: 0.8rem 1rem;
    border-radius: 10px;
    border: none;
    background: #334155;
    color: #fff;
    font-size: 1rem;
  }
  
  input::placeholder {
    color: #94a3b8;
  }
  
  button {
    padding: 0.8rem 1.5rem;
    background: #38bdf8;
    color: white;
    font-weight: 600;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: background 0.2s ease-in-out;
  }
  
  button:hover {
    background: #0ea5e9;
  }
  </style>
  