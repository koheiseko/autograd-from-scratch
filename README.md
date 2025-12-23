# Autograd From Scratch 

Uma implementação minimalista e educacional de um motor de autograd (diferenciação automática) para escalares, construído do zero em Python para entender os fundamentos do backpropagation.

## Motivação

Este projeto nasceu da necessidade de desmistificar uma das "caixas pretas" mais importantes do Deep Learning: o algoritmo de Backpropagation.

Muitas vezes, usamos frameworks como PyTorch ou TensorFlow que abstraem a complexidade matemática. O objetivo aqui foi fazer o caminho inverso: descer o nível de abstração e implementar a matemática "na unha".

Este repositório é o resultado do estudo aprofundado sobre Derivadas e a Regra da Cadeia (Chain Rule), inspirado diretamente pelo tutorial do incrível Andrej Karpathy sobre o micrograd.

## O que ele faz?

O núcleo deste projeto é uma classe (geralmente chamada de Value ou Scalar) que envolve números puros. Ao realizar operações matemáticas com esses objetos, o sistema não apenas calcula o resultado, mas também:

Constrói um Grafo Computacional: Registra quais operações criaram quais valores e quem são seus "pais".

Calcula Gradientes (Backward Pass): Através da chamada do método .backward(), o motor percorre o grafo de trás para frente, aplicando recursivamente a Regra da Cadeia para calcular a derivada do nó final em relação a cada um dos nós anteriores.

## Funcionalidades Principais

Suporte a Operações Escalares: Implementação de operações básicas (+, -, *, /, **) e funções de ativação comuns (Tanh, Exp).

Grafo Dinâmico: O grafo computacional é construído em tempo de execução (run-by-run), similar ao funcionamento do PyTorch.

Backpropagation Automático: Cálculo de gradientes com uma única chamada de função.
