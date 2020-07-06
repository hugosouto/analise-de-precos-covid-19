# Análise de Preçod COVID-19

Análise dos efeitos da pandemia nos preços dos produtos mais comprados pelo Governo Federal no enfrentamento da crise.

## Etapa 1: Extração dos dados no DaaS (Quartzo) SERPRO

A extração dos dados foi reazada no Pentaho Data Integration (v9.0) através do processo "pentaho-precos-covid.ktr".

## Etapa 2: Transformações no RapidMiner

Foram realizados tratamentos estatísticos com o fim dar qualidade às análise feitas.

### Transformações a serem transferidas do RapidMiner para o Pentaho
* Pivô da tabela por UNIDADE_CATMAT
* Pivô da tabela por UNIDADE_CATMAT e COVID
* Filtro count(UNIDADE_CATMAT) > 100
* Filtro standard_deviation(VALOR_UNITARIO) < 100
* Criação de coluna DIFERENCA: 
> ```([median(VALOR_UNITARIO)_Sim]-[median(VALOR_UNITARIO)_Não])/[median(VALOR_UNITARIO)_Não]*100```
* Criação de coluna NORMALIZADO: 
> ```VALOR_UNITARIO-[median(VALOR_UNITARIO)])/[standard_deviation(VALOR_UNITARIO)]```
* Criação de coluna OUTLIER_NOVO:
> ```if(NORMALIZADO>0.2,1,0)```
* Filtro (opcional) para trazer apenas COVID = 0

## Etapa 3: Upload para o Google Planilhas

O arquivo resultante das transformações do RapidMiner são tranformados em planilhas do Google para incorporação dos relatórios do Data Studio.

A planilha deve estar no Drive da conta [delog.copro@gmail.com](https://drive.google.com/drive/folders/1PT1s-thZaZOvt-HdUlksHNAlo_TN2Mno?usp=sharing "Pasta Análise de Preços").

## Etapa 3: Integração com o relatório do Data Studio.

Os dados são adicionados como fonte de dados do relatório: [Análise de Variação de Preços COVID-19](https://datastudio.google.com/reporting/5ccdc714-74c2-4c5f-a4c2-8f9a71223c68 "Análise de Variação de Preços COVID-19").
