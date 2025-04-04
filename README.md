# Buscador de Operadoras ANS - Vue 3

Aplicação frontend desenvolvida em **Vue.js 3** com **Vite**, consumindo uma API FastAPI que retorna dados das operadoras de saúde cadastradas na ANS (Agência Nacional de Saúde Suplementar).

---

## Funcionalidades

- Busca textual por razão social da operadora
- Interface responsiva e moderna
- Comunicação com backend via Axios
- Separação de responsabilidades em componentes reutilizáveis

---

## ▶️ Como rodar o projeto localmente

### 1. Pré-requisitos

Certifique-se de ter instalado:

- **Node.js** v16 ou superior
- **npm** v8 ou superior
- Backend rodando em `http://localhost:8000` com a rota `/operadoras/buscar`

### 2. Siga os passos para executar
- A aplicação será iniciada no endereço: `http://localhost:5173`

```bash
git clone https://github.com/seu-usuario/vue-operadoras.git
cd vue-operadoras
npm install
npm run dev

