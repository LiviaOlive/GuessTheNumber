# 🎲 Guess the Number

> Um jogo interativo de adivinhação desenvolvido inteiramente em portas lógicas.

**Universidade Federal do Cariri (UFCA)** **Disciplina:** Circuitos Digitais  
**Autora:** Ana Lívia Oliveira

---

## 📌 Visão Geral

O projeto **Guess the Number** foi desenvolvido utilizando o simulador **Logisim - ITA**. O objetivo é descobrir um número de 4 bits gerado aleatoriamente pelo sistema. A cada palpite, o circuito fornece um feedback visual através de um sistema de "temperatura" em um LED RGB, indicando o quão perto você está de acertar.

---

## ⚙️ Especificações e Interação

O painel de controle do jogo foi projetado para ser simples e intuitivo:

| Interface | Tipo | Função |
| :--- | :---: | :--- |
| **Botões de Chute** | Entrada | 4 botões para o jogador inserir o palpite em binário (0000 a 1111). |
| **Confirmar** | Entrada | Valida e envia o palpite para análise do circuito. |
| **New** | Entrada | Reinicia o sistema e gera um novo número aleatório. |
| **Display 7 Seg.** | Saída | Exibe o palpite atual convertido para o formato Hexadecimal (0 a F). |
| **LED RGB** | Saída | Indica a proximidade do acerto (mais Azul = distante; mais Vermelho = próximo). |
| **LED Verde** | Saída | Acende exclusivamente quando o jogador adivinha o número exato. |

---

## 🧩 Arquitetura do Sistema

Para organizar a lógica computacional e evitar conflitos de sinal, o circuito `Game` foi modularizado em 4 componentes principais:

* **Comparador $(= / =)$:** Analisa as 4 portas do palpite e as 4 portas do número oculto. Se a igualdade for perfeita, dispara o sinal de vitória para o LED verde.
* **Diferença $(|A - B|)$:** O núcleo matemático do projeto. Utiliza dois subtratores e um multiplexador para calcular a distância absoluta entre o palpite e a resposta real, garantindo sempre uma saída positiva.
* **Cores (Sinal RGB):** Recebe o resultado do circuito de Diferença e converte em sinais de intensidade (8 bits). Quanto menor a diferença numérica, maior a carga enviada ao canal vermelho.
* **Decoder (Display):** Transforma a entrada binária de 4 bits na combinação correta de 7 saídas (a-g) para acender os traços adequados no display hexadecimal.

---

## 🚀 Como Executar o Projeto

1. Certifique-se de ter o Logisim - ITA instalado no seu computador.
2. Faça o download do arquivo do projeto neste repositório.
3. Abra o Logisim, vá em `File > Open` e localize o arquivo.
4. Na barra superior, ative a ferramenta **Alterar Valores** (ícone da mãozinha).
5. Clique nos botões de entrada para jogar!

---
Desenvolvido para avaliação prática da disciplina de Circuitos Digitais, sob a orientação do Prof. Ramon Nepomuceno.
