[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/ARkoM8Jo)
# Diagnóstico de retomada - Aprendizado de Máquina

Esta atividade serve para mapear o que você já domina em Aprendizado de Máquina depois das atividades anteriores da disciplina.

Responda individualmente. Use suas palavras. Rode o código quando possível. Se usar IA depois da primeira tentativa, registre o uso na seção 8.

Prazo: 11/05/2026 às 23:59, horário de Fortaleza.

## 1. Mapa do que eu lembro

Marque cada tópico como: lembro bem, lembro parcialmente, não lembro, nunca vi ou não tenho certeza.

- vetores, matrizes e produto escalar: lembro bem
- média, desvio padrão e correlação:lembro bem
- probabilidade condicional e Teorema de Bayes:não lembro
- regressão linear:lembro parcialmente
- classificação supervisionada:lembro parcialmente
- treino, teste e validação:lembro bem
- normalização ou padronização de dados:lembro bem
- KNN:não lembro
- árvore de decisão:lembro bem
- matriz de confusão:lembro bem
- acurácia, precisão, recall e F1-score:lembro bem
- overfitting e underfitting:não lembro
- validação cruzada:lembro parcialmente
- Random Forest:lembro bem
- XGBoost ou boosting:lembro bem
- `predict_proba()`:lembro parcialmente
- SQL/ETL aplicado a dados:lembro bem
- simulação de Monte Carlo:lembro parcialmente

## 2. O que foi trabalhado antes

Explique, em 8 a 12 linhas:

1. quais desses tópicos você lembra de ter trabalhado na disciplina;
2. quais atividades ou exemplos você lembra;
3. o que você conseguiu fazer com autonomia;
4. o que você só conseguiu fazer seguindo roteiro;
5. qual assunto precisa ser retomado com mais urgência.

Realizamos atividades usando numpy, pandas, matplot para os primeiros assuntos citados, atividades de resolução de algumas perguntas matematicas junto com teoria e aplicação. Foi feito um modelo de classificação com random forest e XGboost, as atividades eram feitas em grupo, normalmente ficava na parte escrita teorica, porém fiz a maior parte do codigo de regressão linear para predição de valor imobiliario, e o modelo de predição de doenças(especificamente asma). Grande parte foi feito com autonomia, utilizando IA apenas para busca de funções e aplicações de funções. Já tinhamos visto parte desse conteúdo na disciplina de IA. No ultimo trabalho cobrado na disciplina foi um modelo de predição para campeonato de futebol, onde utilizamos random forest e xgboost, o xgboost foi utilizado numa tentativa de prever empates. Nesse mesmo trabalho utilizamos a simulação de monte carlo, mas não foi minha parte então não lembro bem. KNN não lembro de ter sido explicada/ aprofundada. SQL/ETL também foi utilizado nesse último trabalho, porém já é algo que estou mais habituado de estudos autonomos e outras materias.

## 3. Conceitos essenciais

Responda com suas palavras e dê um exemplo simples.

1. O que é aprendizado supervisionado?
   Utilizar dados selecionados para treinamento de um modelo de predição, onde é explicada a relação entre os dados para que seja utilizado com dados novos e maior precisão. Ex. Treinar um modelo de prever doenças no coração com exames de pacientes que realmente tem e pacientes que não tem, para testar a precisão do modelo.
3. O que é uma tarefa de classificação?
   a pratica do aprendizado supervisionado
5. O que são features e target?
   caracteristicas e alvo(resultado real que o modelo precisa prever) ex. paciente que reamente tem o problema diagnosticado vs o que não tem
7. Para que serve separar treino e teste?
   Para que tenha certeza que ele pode identificar os mesmo padrões identificados no treino, só que no teste
9. Por que acurácia pode ser uma métrica enganosa?
    não lembro

## 4. Diagnóstico prático com Scikit-Learn

No arquivo `diagnostico_ml.py`, use o dataset `load_breast_cancer` do Scikit-Learn e faça:

1. carregue os dados;
2. separe `X` e `y`;
3. divida em treino e teste;
4. treine uma regressão logística;
5. treine uma árvore de decisão;
6. mostre matriz de confusão, acurácia, precisão, recall e F1-score para cada modelo;
7. compare o desempenho em treino e teste;
8. escreva aqui qual modelo generalizou melhor e por quê.

Se não conseguir terminar tudo, registre até onde chegou e qual erro apareceu.

### Resultados

Cole aqui os principais resultados do seu código.

```text
=== Regressão logística ===
Acurácia treino: 0.958
Acurácia teste: 0.958
Precisão teste: 0.947
Recall teste: 0.989
F1-score teste: 0.967
Matriz de confusão:
[[48  5]
 [ 1 89]]
Probabilidades das 5 primeiras amostras de teste:
[[0.01854698 0.98145302]
 [0.99816861 0.00183139]
 [0.17716357 0.82283643]
 [0.2344741  0.7655259 ]
 [0.19796601 0.80203399]]

=== Árvore de decisão ===
Acurácia treino: 1.000
Acurácia teste: 0.923
Precisão teste: 0.954
Recall teste: 0.922
F1-score teste: 0.938
Matriz de confusão:
[[49  4]
 [ 7 83]]
Probabilidades das 5 primeiras amostras de teste:
[[0. 1.]
 [1. 0.]
 [1. 0.]
 [0. 1.]
 [0. 1.]]
```

### Interpretação

Qual modelo generalizou melhor? Explique usando as métricas e a comparação entre treino e teste.

Resposta:Nesse caso o modelo logistico generalizou melhor, o resultado obtido no teste foi igual ao do treino, o que indica boa memorização/identificação de padrões,
mesmo que a arvore também tenha tido um bom resulado, a diferença entre teste e treino é maior.

## 5. Probabilidade e interpretação

Escolha um dos modelos treinados e responda: logistico

1. O modelo produz probabilidade com `predict_proba()`?
2. O que significa uma probabilidade alta para uma classe?
3. Probabilidade alta garante que a previsão está correta? Explique.
4. Em um problema real, qual seria o risco de confiar cegamente nessa previsão?

Resposta: Sim. Significa maior chance de ser a predição correta, mas assim como todo modelo não há como indicar uma previsão correta com 100% de certeza.
Alto, não se confia cegamente em predição nenhuma, existem milhares de outros fatores que podem não ter sido considerados.

## 6. Generalização

Compare treino e teste: 

1. Há sinal de overfitting? 
2. Há sinal de underfitting? 
3. O que você tentaria mudar para melhorar o resultado?
4. O que você precisaria estudar melhor para responder com mais segurança? Interpretação de dados e termos, tecnicas. Pois não lembro nem o que é overfitting.

Resposta: 4. Interpretação/compreensão de dados/resultados e termos, tecnicas. Pois não lembro nem o que é overfitting.

## 7. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva: overfitting e underfitting

1. o que você entende dele; 
2. onde você se confunde; 
3. que tipo de explicação ajudaria: 

Resposta: 1. Algo sobre os testes e treinos, mas não lembro a definição correta/exata.
2. Preciso rever tudo.
3. exemplo no quadro, exercício curto, visualização ou projeto pequeno.

## 8. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:

```text
Pergunta feita: como eu sei que um modelo de aprendizado generalizou bem?
Resumo da resposta: Um modelo de aprendizado de máquina “generalizou bem” quando ele consegue ter um bom desempenho em dados novos, e não apenas nos dados usados no treinamento.
Como eu verifiquei: 
O que eu alterei na minha resposta:
O que ainda não entendi:
```

## Submissão no Moodle

Depois de finalizar, copie no Moodle:

```text
Repositório:
Commit final:
Autoavaliação: nível atual, maior dificuldade e tópico que precisa ser retomado.
```
