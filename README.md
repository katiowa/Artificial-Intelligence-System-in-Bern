# 🧠 Bern Neural Network Demo

Este projeto é uma demonstração de **Inteligência Artificial (Rede Neural)** implementada nativamente na linguagem **Bern**. O objetivo é testar a maturidade do compilador, a estabilidade de cálculos em ponto flutuante e a manipulação de estruturas de dados complexas.

## 🚀 Visão Geral

O projeto implementa um **Perceptron de Camada Única** treinado via **Backpropagation** e **Gradient Descent**. Através de uma interface gamificada no terminal, o usuário pode "ensinar" lógica matemática para a linguagem, definindo tabelas da verdade customizadas (como as portas lógicas AND, OR, NAND, etc).

## 📁 Estrutura do Projeto

O sistema é dividido em três módulos principais:

*   **`lib/matrix.brn`**: Uma biblioteca de Álgebra Linear. Embora o neurônio atual utilize cálculos escalares para otimização, esta lib fornece a base para operações com matrizes (soma, transposição e multiplicação), essencial para futuras implementações de *Deep Learning* e sistemas de física.
*   **`lib/brain.brn`**: O núcleo da IA. Contém a implementação da função de ativação **Sigmoid** (com travas de segurança para estabilidade numérica), o cálculo da derivada e o algoritmo de ajuste de pesos.
*   **`Main.brn`**: Interface interativa de usuário. Permite a entrada de dados, treinamento em massa (1000+ épocas) e teste de previsões com interpretador de probabilidades.

## 🛠️ Detalhes Técnicos

### O Algoritmo de Aprendizado
A IA aprende através do ajuste iterativo de **Weights** (pesos) e **Bias** (viés). A cada época de treinamento:
1.  **Forward Pass**: O neurônio faz uma previsão baseada nas entradas atuais.
2.  **Cálculo do Erro**: O sistema compara a previsão com o gabarito definido pelo usuário.
3.  **Backpropagation**: Utilizando a derivada da função Sigmoid, o sistema calcula o gradiente e ajusta os pesos para minimizar o erro na próxima iteração.

### Estabilidade Numérica
Foi implementada uma função `safe_sigmoid` para garantir que o sistema lide corretamente com os limites de precisão da série de Taylor do comando `exp()`, mantendo os resultados confiaveis dentro do intervalo `[0, 1]`.

## 🎮 Como Rodar

Certifique-se de ter o interpretador `Bern.exe` no seu PATH e os arquivos na estrutura correta, então execute:

```bash
Bern.exe Main.brn
```
