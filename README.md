# Banco API Performance

Projeto de automação de testes de performance desenvolvido com **JavaScript** e **K6** para validar o desempenho da API REST do projeto **Banco API**.

Repositório da API testada:

https://github.com/juliodelimas/banco-api

Repositório deste projeto:

https://github.com/Leandrordsc/banco-api-performance

---

# Introdução

Este projeto foi desenvolvido com o objetivo de executar testes de performance na API REST do Banco API utilizando o **K6**.

Os cenários simulam múltiplos usuários virtuais (VUs), permitindo avaliar tempo de resposta, throughput, falhas e comportamento da API sob carga.

---

# Funcionalidades

Este projeto permite:

- Executar testes de carga utilizando K6.
- Configurar a URL da API através da variável `BASE_URL`.
- Executar cenários independentes.
- Acompanhar métricas de desempenho em tempo real.
- Exportar o resumo da execução em formato JSON.
- Facilitar a integração com pipelines de CI/CD.

---

# Tecnologias Utilizadas

- JavaScript (ES6)
- K6
- Node.js
- Git
- GitHub

---

# Estrutura do Repositório

```text
banco-api-performance/
├── helpers/
├── config/
├── tests/
├── utils/
├── .gitignore
├── summary.json
└── README.md
```

---

# Objetivo de Cada Grupo de Arquivos

## config/

Arquivos responsáveis pelas configurações utilizadas durante a execução dos testes, como opções de carga, thresholds e variáveis compartilhadas.

## helpers/

Funções auxiliares reutilizadas pelos cenários de teste.

## tests/

Contém os cenários de testes de performance escritos em JavaScript utilizando o K6.

## utils/

Funções utilitárias utilizadas pelos testes.

## summary.json

Arquivo gerado pelo K6 contendo o resumo da execução dos testes.

---

# Modo de Instalação

```bash
git clone https://github.com/Leandrordsc/banco-api-performance.git
cd banco-api-performance
npm install
```

Instale o K6:

https://k6.io/docs/get-started/installation/

Verifique:

```bash
k6 version
```

---

# Configuração

> **Importante**

Antes de executar qualquer teste é obrigatório definir a variável de ambiente:

```text
BASE_URL=http://localhost:3000
```

---

# Execução dos Testes

### Windows (PowerShell)

```powershell
$env:BASE_URL="http://localhost:3000"
k6 run tests/login.js
```

### Windows (CMD)

```cmd
set BASE_URL=http://localhost:3000
k6 run tests/login.js
```

### Linux/macOS

```bash
BASE_URL=http://localhost:3000 k6 run tests/login.js
```

---

# Relatório em Tempo Real

Durante a execução, o K6 exibe métricas em tempo real diretamente no terminal.

---

# Exportação do Relatório

```powershell
$env:BASE_URL="http://localhost:3000"
k6 run --summary-export=summary.json tests/login.js
```

Também é possível exportar em JSON:

```powershell
$env:BASE_URL="http://localhost:3000"
k6 run tests/login.js --out json=summary.json
```

---

# Documentação

- K6: https://k6.io/docs/
- JavaScript: https://developer.mozilla.org/docs/Web/JavaScript
- Git: https://git-scm.com/docs

---

# Autor

Leandro Rodrigues

GitHub:
https://github.com/Leandrordsc
