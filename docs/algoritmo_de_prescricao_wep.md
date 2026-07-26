# 🧠 Algoritmo de Prescrição e Distribuição (Motor Cascata 2.0)

Este documento detalha o **Work Engine/Distribution (WEP)**, batizado internamente de **Motor Cascata 2.0**. Ele é o cérebro matemático responsável por receber os *inputs* de exercícios, calcular as interseções de volume indireto e distribuir as séries de forma otimizada na rotina do usuário.

---

## 🤖 Geração Inteligente e Fluxo do Usuário

O sistema oferece uma flexibilidade de interface dividida em duas abordagens de uso:

### 1. Seleção Manual Orientada

O usuário navega pela biblioteca de exercícios e seleciona opções que preencham os **Perfis Biomecânicos** obrigatórios de cada grupamento muscular (ex.: um perfil alongado, um encurtado e um neutro).

### 2. Auto-Fill (IA Biomecânica)

Um algoritmo gerador injeta, de forma *hardcoded*, as melhores seleções biomecânicas com base na divisão de treino escolhida (ex.: *Full Body*, *Push/Pull/Legs*). O usuário recebe uma rotina otimizada instantaneamente, mantendo a liberdade de alterar qualquer exercício individualmente antes da compilação final.

---

## 🔄 O Motor de Cascata (Iterações de Convergência)

Diferentemente de calculadoras estáticas, a compilação do treino não ocorre de forma linear. Ao clicar em **Gerar Treino**, o **Motor Cascata 2.0** entra em execução.

Como os exercícios geram frações decimais de volume indireto (por exemplo, um *Supino Inclinado* gera `1.0` de Peitoral e `0.45` de Tríceps), o sistema precisa transformar essas frações em séries exatas (inteiras) praticáveis na academia.

### Ciclo de Reequilíbrio

O motor realiza múltiplas iterações de checagem (geralmente convergindo na **Iteração 6**). Em cada ciclo, ele:

1. Soma o volume direto e indireto de todos os exercícios.
2. Compara o volume estimado com o **Volume Alvo (Meta)** de cada grupamento muscular.
3. Ajusta dinamicamente a quantidade de séries de cada exercício para cima ou para baixo.
4. Repete o processo até que todos os músculos atinjam a meta mais próxima possível utilizando apenas números inteiros de séries.

---

## ✂️ Função de Poda (*Pruning*) e Volume Indireto

O motor processa rigorosamente a **Matriz de Coeficientes Indiretos**. Durante as iterações, ele mapeia o impacto sistêmico que os exercícios compostos geram nos grupamentos acessórios (como Tríceps, Antebraços e Glúteos).

### Exemplo de impacto (saída real do sistema)

```text
◈ GLÚTEOS:
  🔗 [Stiff]      -> P1 +3.1 sets
  🔗 [Leg Press]  -> P1 +2.7 sets
  🔗 [Passada]    -> P1 +1.5 sets
```

Se a meta de volume de um grupamento muscular acessório ou opcional (como Glúteos ou Antebraços) for integralmente atingida apenas pelo somatório dos impactos indiretos dos exercícios base (como Stiff e Leg Press), o sistema executa a **Poda Lógica**.

Nessa etapa, ele automaticamente remove (ou oculta) exercícios de isolamento daquele grupamento da ficha final, evitando **overtraining** (excesso de volume) e mantendo a rotina eficiente, sustentável e biomecanicamente equilibrada.

---

## 📅 Distribuição da Rotina

Após calcular a quantidade final de séries, o **Motor Cascata 2.0** distribui automaticamente o volume ao longo da semana conforme o *split* escolhido.

Por exemplo, em um **Full Body** de cinco dias, o algoritmo garante que exercícios de Costas e Quadríceps sejam distribuídos uniformemente entre as sessões, reduzindo a fadiga central, controlando a sobreposição de estímulos e otimizando a recuperação entre os treinos.
