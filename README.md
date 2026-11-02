# TV ou busca paga: para onde testar a transferência de verba de mídia exterior?

Estudo de caso de Rhenan Amorim sobre alocação de orçamento entre canais. Usei os dados de demonstração do projeto Robyn, da Meta. A receita e os investimentos são simulados, e a base não identifica uma empresa anunciante nem um produto específico.

**[Abrir o estudo de caso](https://rhenan-amorim.github.io/robyn-mix-de-midia/)**

## A decisão de marketing

Se um anunciante deslocasse 5% da verba semanal de mídia exterior, valeria testar TV ou busca paga? Comparei as duas alternativas com a distribuição original, mantendo o mesmo orçamento total em cada semana.

| Plano | Receita adicional estimada em relação à distribuição original¹ |
|---|---:|
| Manter a distribuição | 0 |
| Transferir para TV | 1,02 milhão |
| Transferir para busca paga | 1,55 milhão |

¹ Mediana entre 24 configurações de modelo, em unidades monetárias simuladas. As estimativas para busca variaram de 0,70 a 3,96 milhões. Em cada comparação sob as mesmas hipóteses, busca ficou à frente de TV.

## Como cheguei ao resultado

1. **Escolhi semanas comparáveis.** Das 208 semanas da base, 34 permitiam transferir verba para qualquer um dos dois destinos sem ultrapassar a faixa histórica de gasto positivo de cada canal.
2. **Validei a previsão em ordem cronológica.** Nas 104 semanas de avaliação, adicionar os cinco canais ao calendário reduziu o erro absoluto ponderado pela receita (WAPE) de 14,9% para 13,2%. A mídia melhorou a previsão em três dos quatro blocos.
3. **Testei a sensibilidade da decisão.** Ajustei regressões em Python e variei a duração do efeito da publicidade, a resposta a aumentos de investimento e a penalização dos coeficientes. A página inclui as 24 configurações e o download dos resultados em CSV.

## Recomendação

Eu testaria primeiro a transferência para busca paga em mercados comparáveis, sorteando quais manteriam a verba original. A decisão de expansão dependeria da receita adicional observada durante o teste e após a última transferência. A simulação prioriza essa hipótese; o efeito causal em uma operação real permanece em aberto.

**Fonte dos dados:** [série semanal de demonstração do Meta Robyn](https://github.com/facebookexperimental/Robyn/blob/main/python/src/robyn/tutorials/resources/dt_simulated_weekly.csv).
