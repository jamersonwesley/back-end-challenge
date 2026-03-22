# 💱 Back-end Challenge - Conversor de Moeda

API desenvolvida em PHP para conversão de moedas, como parte do desafio técnico da Apiki.

---

## 🚀 Tecnologias utilizadas

* PHP 7.4
* Docker
* Composer
* Codeception (testes automatizados)
* PHP CodeSniffer (PSR-12)

---

## 📦 Como rodar o projeto

### 🔧 1. Clonar o repositório

```bash
git clone <url-do-repositorio>
cd back-end-challenge
```

---

### 🐳 2. Subir o projeto com Docker

```bash
docker-compose up --build
```

A aplicação estará disponível em:

```
http://localhost:8000
```

---

## 🔥 Como usar a API

### 📌 Endpoint

```
GET /{valor}/{moeda_origem}/{moeda_destino}/{taxa}
```

### 📌 Exemplo

```bash
http://localhost:8000/10/BRL/USD/0.5
```

### 📌 Resposta

```json
{
  "valorConvertido": 5.00,
  "simboloMoeda": "$"
}
```

---

## 🧪 Rodando os testes

### 🔍 Acessar o container

```bash
docker ps
docker exec -it <nome_do_container> bash
```

### ▶️ Executar testes

```bash
composer test
```

---

## 🧹 Padrão de código (Lint)

Verificar padrões:

```bash
composer lint
```

Corrigir automaticamente:

```bash
composer fix
```

---

## 📂 Estrutura do projeto

```
.
├── src/
│   └── index.php
├── tests/
│   ├── Api/
│   │   └── ApiCest.php
│   └── Api.suite.yml
├── docker-compose.yml
├── Dockerfile
└── composer.json
```

---

## ⚙️ Regras de negócio

* O valor deve ser numérico e maior que zero
* A taxa deve ser numérica e maior que zero
* As moedas devem estar em formato **ISO (3 letras maiúsculas)**
* Conversões suportadas:

  * BRL → USD
  * USD → BRL
  * BRL → EUR
  * EUR → BRL

---

## ❌ Tratamento de erros

A API retorna HTTP 400 para:

* Parâmetros inválidos
* Valores negativos
* Moedas inválidas
* Conversões não suportadas

---

## 🧠 Decisões técnicas

* Uso do **PHP Built-in Server com router** para simplificar o roteamento
* Containerização com Docker para garantir consistência de ambiente
* Testes automatizados com Codeception garantindo cobertura de cenários

---

## 🏁 Status

✅ Testes passando
✅ Lint aprovado (PSR-12)
✅ Pronto para produção/teste técnico

---

## 👨‍💻 Autor

**Jamerson Wesley**
📧 [jamersonwesleyoliveira@gmail.com](mailto:jamersonwesleyoliveira@gmail.com)
🔗 https://github.com/apiki/back-end-challenge

---
