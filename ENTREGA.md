# Entrega — Trabalho Final: melhorando o `clima_pipeline`

## Grupo / Integrantes
- **Nome:** Charles (e integrantes do grupo)

---

## Funcionalidade 1 — Novas cidades e sensação térmica

### Checklist

- [x] O pipeline rodou para as **7 cidades** e terminou com "Pipeline concluído".
- [x] No banco, a tabela `clima_diario` contém registros para todas as 7 cidades (incluindo Belém e Curitiba).
- [x] As colunas `sensacao_media` e `sensacao_max` estão presentes e preenchidas na tabela `clima_diario`.
- [x] A API devolve `sensacao_media` e `sensacao_max` no endpoint GET `/clima/diario`.
- [x] A API continua funcionando para `/cidades` e `/health`.
- [x] O dashboard exibe as novas métricas de sensação térmica (médias e máximas) e permite filtrar por cidade (incluindo Belém e Curitiba).

### Evidências em Prints
- `prints/pipeline_7_cidades.png` — Logs do pipeline executando e concluindo para as 7 cidades.
- `prints/banco_sensacao_belem.png` — Consulta SQLite mostrando registros de Belém com colunas `sensacao_media` e `sensacao_max`.
- `prints/api_cidades_7.png` — Resposta do endpoint GET `/cidades` listando 7 cidades.
- `prints/api_diario_sensacao.png` — Resposta do endpoint GET `/clima/diario` contendo os novos campos de sensação térmica.
- `prints/dashboard_sensacao_curitiba.png` — Dashboard Streamlit exibindo dados de Curitiba com sensação térmica.
- `prints/testes_mock_func1.png` — Testes executados com dados mockados para as transformações da Funcionalidade 1.

---

## Funcionalidade 2 — Resumo estatístico do período

### Checklist

- [x] Existe uma nova transformação que calcula o resumo estatístico por cidade no período (média das médias, máxima das máximas, mínima das mínimas, etc.).
- [x] Existe um novo endpoint na API GET `/clima/resumo` que aceita parâmetros `cidade`, `inicio` e `fim`.
- [x] O dashboard possui uma visão/seção de **Resumo do Período** usando o novo endpoint (ou lógica de resumo).
- [x] A lógica de filtragem por período de uma cidade está centralizada (sem código duplicado).
- [x] Testes com dados falsos validadam os cálculos do resumo estatístico.
- [x] README e documentação (Sphinx) atualizados com as instruções do novo endpoint.

### Evidências em Prints
- `prints/api_resumo_sucesso.png` — Resposta do endpoint GET `/clima/resumo` com o resumo estatístico de um período.
- `prints/api_resumo_validacao_datas.png` — Validação de datas inválidas no endpoint `/clima/resumo` (ex: `inicio` > `fim`).
- `prints/codigo_filtrar_periodo_unico.png` — Código fonte com a função de filtragem por período centralizada.
- `prints/dashboard_cartoes_resumo.png` — Cartões e resumos estatísticos exibidos no dashboard.
- `prints/dashboard_resumo_filtro_data.png` — Reatividade do dashboard ao alterar os filtros de data.
- `prints/docs_readme_atualizados.png` — Documentação Sphinx e README atualizados.

---

## Reflexão Curta
A refatoração permitiu expandir a cobertura geográfica do pipeline ETL de 5 para 7 cidades sem comprometer a estabilidade do sistema. A adição das métricas de sensação térmica trouxe maior utilidade analítica aos dados meteorológicos, e o novo endpoint de resumo estatístico otimizou o consumo de dados aglutinados pelo frontend Streamlit.
