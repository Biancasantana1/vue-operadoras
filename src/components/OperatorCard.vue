<template>
    <li class="operator-card">
      <p class="operator-title">{{ operator.razao_social }}</p>
  
      <p v-if="operator.nome_fantasia" class="operator-sub">
        {{ operator.nome_fantasia }} — {{ operator.modalidade }}
      </p>
      <p v-else class="operator-sub">
        {{ operator.modalidade }}
      </p>
  
      <p class="operator-location">
        <svg class="icon-location" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24">
          <path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5S10.62 6.5 12 6.5s2.5 1.12 2.5 2.5S13.38 11.5 12 11.5z" />
        </svg>
        {{ operator.cidade }} / {{ operator.uf }}
      </p>
  
      <p class="operator-id">
        <svg class="icon-id" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24">
          <path d="M4 4h16v16H4V4zm2 2v12h12V6H6zm2 2h2v2H8V8zm0 3h4v1H8v-1zm0 2h4v1H8v-1z"/>
        </svg>
        Registro ANS: {{ operator.registro_ans }}
      </p>
    </li>
  </template>
  
  <script>
  export default {
    name: "OperatorCard",
    props: {
      operator: {
        type: Object,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .operator-card {
    background: rgba(255, 255, 255, 0.05);
    padding: 1.2rem;
    margin-bottom: 1rem;
    border-radius: 12px;
    border: 1px solid #475569;
  }
  
  .operator-title {
    font-weight: bold;
    font-size: 1.1rem;
    color: #38bdf8;
  }
  
  .operator-sub {
    font-size: 0.95rem;
    color: #e2e8f0;
  }
  
  .operator-location {
    margin-top: 0.3rem;
    font-size: 0.9rem;
    color: #e2e8f0;
    display: flex;
    align-items: center;
  }
  
  .icon-location {
    width: 1rem;
    height: 1rem;
    margin-right: 6px;
    color: #38bdf8;
  }
  
  .operator-id {
    margin-top: 0.4rem;
    font-size: 0.85rem;
    color: #e2e8f0;
    display: flex;
    align-items: center;
  }
  
  .icon-id {
    width: 1rem;
    height: 1rem;
    margin-right: 0.4rem;
    color: #facc15;
  }
  </style>
  