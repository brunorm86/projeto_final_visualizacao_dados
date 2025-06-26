
# Análise Estatística: Relação entre IDH, Partidos Políticos e Cobertura Vacinal nos Municípios Brasileiros

------------

### Projeto final da Disciplina "Visualização de Dados", UFSC Araranguá, Curso TIC, Semestre 2025/1

-----------------------
## 📌 Objetivo

Este projeto tem como objetivo investigar se há relação significativa entre:

- o **Índice de Desenvolvimento Humano (IDH)** dos estados brasileiros,
- os **partidos políticos mais votados** nas eleições de 2022 (1º turno),
- e a **cobertura vacinal** dos estados e municípios no ano de 2023.

De forma geral, buscamos responder à pergunta:  
> **"Há relação entre IDH, comportamento eleitoral e cobertura vacinal no Brasil?"**

De forma específica:
>1. Existe relação entre IDH e cobertura vacinal dos estados? Qual?
>2. Municípios com alta votação em candidatos de partidos com discurso antivacina em 2022 apresentaram menor índice de vacinação em 2023?
>3. Quais os três partidos mais votados nos cinco estados com maior IDH e nos cinco com menor IDH?
>4. Quais partidos foram mais votados nos estados com menor cobertura vacinal? E nos com maior?
>5. Formalmente, podemos afirmar que de fato há relação entre IDH, partidos mais votados e cobertura vacinal?

---

## 📊 Base de Dados

- **Cobertura vacinal** por município (Ministério da Saúde, 2023)
- **Resultado das eleições de 2022** por município e partido (TSE)
- **IDH dos estados brasileiros (2021)** — Atlas Brasil / PNUD

---

## 🧪 Metodologia

### 1. **Pré-processamento**
- Unificação e padronização de nomes de municípios e estados.
- Classificação dos partidos com discurso antivacina: `['PL', 'PTB', 'PSC', 'PP', 'REPUBLICANOS']`.
- Categorização dos municípios de acordo com o **partido mais votado**.
- Inclusão do IDH estadual como proxy de desenvolvimento local.

### 2. **Análise Estatística**
Foram construídos dois modelos de regressão linear:

#### 🔹 Modelo 1 — com IDH categorizado
- `COBERTURA_VACINAL ~ IDH_categorizado + ANTIVACINA + Interação`
- R² ≈ 0.287 (explica ~28,7% da variação)
- **IDH** mostrou-se fortemente associado à cobertura vacinal.
- **Partido antivacina** e sua **interação com IDH** não foram estatisticamente significativos.

#### 🔹 Modelo 2 — com IDH contínuo
- `COBERTURA_VACINAL ~ IDH_contínuo + ANTIVACINA + Interação`
- R² ≈ 0.078 (explica ~7,8% da variação)
- IDH contínuo mostrou associação negativa significativa com a cobertura vacinal (coef. = -56.88), embora contraintuitiva.
- Partido antivacina e interação novamente **não foram significativos**.

---

## 📈 Visualizações

Foram criados gráficos interativos com **Plotly**, incluindo:

- Dispersão da cobertura vacinal vs IDH, colorida por partido antivacina.
- Barras comparando partidos mais votados nos estados com maior e menor cobertura vacinal.
- Pizza com distribuição dos partidos mais votados por grupo.

---

## ✅ Conclusões

- **IDH** influencia a cobertura vacinal, mas o sinal negativo em modelos contínuos sugere possível influência de outros fatores (região, cultura, renda).
- A **votação em partidos com discurso antivacina** não demonstrou efeito estatisticamente significativo direto sobre a cobertura vacinal nos modelos aplicados.
- **Interações entre IDH e partido também não foram significativas**.
- Mais variáveis são necessárias para explicar de forma robusta a variação na vacinação, como escolaridade, região, acesso a saúde e campanhas locais.

---

## 📁 Estrutura do Projeto

```
.
├── data/
│   ├── idh_estados_2021.csv
│   ├── cobertura_vacinal_municipios_2023.csv
│   └── votacao_partido_munzona_2022_BRASIL.csv
├── projeto.ipynb
├── README.md
└── requirements.txt
```

---

## 📌 Requisitos

Instale as dependências com:

```bash
pip install -r requirements.txt
```

---

## 📬 Contato

- [Bruno Ricardo Machado](https://www.instagram.com/brunorm86/)
- [Github](https://github.com/brunorm86)
- [Linkedin](https://www.linkedin.com/in/bruno-ricardo-machado/)
- [E-Mail](mailto:brunorm869@gmail.com)
---
