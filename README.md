# Análise de Preçod COVID-19

Análise dos efeitos da pandemia nos preços dos produtos mais comprados pelo Governo Federal no enfrentamento da crise.

## Etapa 1: Extração dos dados no DaaS (Quartzo) SERPRO

A extração dos dados foi reazada no Pentaho Data Integration (v9.0) através do processo "pentaho-precos-covid.ktr".

## Etapa 2: Transformações no RapidMiner

Foram realizados tratamentos estatísticos com o fim dar qualidade às análise feitas.

## Etapa 3: Upload para o Google Planilhas

O arquivo resultante das transformações do RapidMiner são tranformados em planilhas do Google para incorporação dos relatórios do Data Studio.

## Etapa 3: Integração com o relatório do Data Studio.

Os dados são adicionados como fonte de dados do relatório: https://datastudio.google.com/reporting/5ccdc714-74c2-4c5f-a4c2-8f9a71223c68.
