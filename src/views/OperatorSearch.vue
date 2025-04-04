<template>
  <div class="container">
    <div class="card-container">
      <h1 class="title">🔍 Buscar Operadora</h1>

      <SearchForm v-model="query" @search="fetchOperators" />

      <div v-if="loading" class="loading">Buscando...</div>

      <div v-else-if="operators.length" class="results">
        <h2>Resultados</h2>
        <ul>
          <OperatorCard
            v-for="op in operators"
            :key="op.ans_registration"
            :operator="op"
          />
        </ul>
      </div>

      <div v-else-if="hasSearched && !operators.length" class="not-found">
        Nenhuma operadora encontrada.
      </div>
    </div>
  </div>
</template>

<script>
import SearchForm from "../components/SearchForm.vue";
import OperatorCard from "../components/OperatorCard.vue";
import api from "../services/api";
import { ENDPOINTS } from "../services/api";


export default {
  name: "OperatorSearch",
  components: {
    SearchForm,
    OperatorCard
  },
  data() {
    return {
      query: "",
      operators: [],
      loading: false,
      hasSearched: false
    };
  },
  methods: {
    async fetchOperators() {
      if (!this.query.trim()) return;

      this.loading = true;
      this.hasSearched = false;

      try {
        const res = await api.get(ENDPOINTS.searchOperators, {
        params: { query: this.query }
        });
        this.operators = res.data;
      } catch (err) {
        console.error("Erro ao buscar operadoras:", err);
        this.operators = [];
      } finally {
        this.loading = false;
        this.hasSearched = true;
      }
    }
  }
};
</script>

<style scoped src="../styles/operator.css" />
