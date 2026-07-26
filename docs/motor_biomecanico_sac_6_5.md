# ⚙️ Motor Biomecânico e Sistema de Auditoria de Carga (SAC 6.5)

Este documento descreve o núcleo lógico e matemático responsável por quantificar o estímulo de treinamento dentro da plataforma **Transforme Tudo**.

O **Sistema de Auditoria de Carga (SAC 6.5)** é uma metodologia biomecânica determinística projetada para converter exercícios físicos em uma unidade computacional padronizada denominada **Equivalência de Série ($S_e$)**.

O sistema não utiliza heurísticas subjetivas (como "fadiga percebida" ou "esforço"). Ele avalia exclusivamente a eficiência com que a tensão mecânica gerada pela carga externa é transferida para o músculo-alvo durante uma série levada à falha técnica.

---

## 📐 O Axioma Fundamental

O valor máximo possível do sistema é definido como **1.0 $S_e$** (*Série Integral*). Este teto físico ocorre exclusivamente quando a falha concêntrica é diretamente ditada pela incapacidade do músculo auditado, sem que a estabilidade do corpo ou a trajetória da carga atuem como elos limitantes da produção de força. Nenhum exercício pode exceder o valor de **1.0 $S_e$**.

---

## 🧠 Matriz Universal de Auditoria (Critérios C1 a C6)

A avaliação da eficiência mecânica de um movimento ocorre através de uma matriz binária. Cada critério recebe `1` (satisfeito) ou `0` (não satisfeito). O modelo atua sobre as propriedades estruturais inerentes ao exercício.

1. **C1 — Ação Dinâmica:** O músculo realiza encurtamento e alongamento ativo sob carga (produção de trabalho mecânico). Se **C1 = 0** (trabalho puramente isométrico), o coeficiente sofre travamento algorítmico em **0.30** no máximo.

2. **C2 — Torque Estrutural:** O músculo atua como motor primário ou co-primário (sua remoção tornaria o movimento mecanicamente impossível).

3. **C3 — Elo Limitante Estrutural:** O músculo é estruturalmente necessário para completar a fase concêntrica, sendo ele próprio o motivo mecânico da falha.

4. **C4 — Tensão em Alongamento:** O ponto de inversão excêntrico-concêntrico ocorre com o músculo em posição alongada (estiramento sob carga máxima).

5. **C5 — Estabilidade de Vetor:** A trajetória da carga é guiada externamente (ex.: polias, máquinas ou trilhos do Smith), eliminando graus de liberdade.

6. **C6 — Estabilidade Sistêmica:** A estabilização ativa do corpo humano não representa uma camada de limitação relevante para a produção de torque no músculo auditado (ex.: o tronco está apoiado ou ancorado em um banco).

---

## 📊 Tabela Oficial de Conversão Computacional

O somatório dos critérios binários (**Score**) é mapeado diretamente para o valor final em ponto flutuante ($S_e$) da Equivalência de Série.

| Score Binário | Coeficiente ($S_e$) | Classificação do Estímulo |
|:-------------:|:-------------------:|---------------------------|
| **6** | **1.0** | Série Integral (Padrão Ouro / Transferência Máxima) |
| **5** | **0.8** | Composto Dominante (Alta Eficiência) |
| **4** | **0.6** | Dominante com Limitação Sistêmica ou de Vetor |
| **3** | **0.45** | Sinergista Forte |
| **2** | **0.30** | Sinergista Moderado |
| **1** | **0.15** | Estabilizador Ativo / Residual |
| **0** | **0.00** | Nulo |

---

## 🧭 SDV 2.0 — Sistema Determinístico de Dominância de Torque

Para gerenciar interseções complexas — como o grupamento de Costas, que divide o volume entre **Tração Vertical** (Latíssimo do Dorso) e **Tração Horizontal** (Espessura) — o motor aplica o **SDV 2.0**.

O SDV avalia a direção do vetor de tração e a obrigatoriedade mecânica de retração escapular, distribuindo a **Equivalência de Série ($S_e$)** com proporções fixas pré-processadas.

### Exemplos

- **Remada Curvada:** vetor horizontal com necessidade estrutural de retração escapular (**Perfil Horizontal: 65%** / **Perfil Vertical: 35%**).

- **Puxada Frontal:** vetor predominantemente vertical, em que a retração escapular não é o elo limitante (**Perfil Vertical: 75%** / **Perfil Horizontal: 25%**).

Essa determinação algorítmica permite que o motor desconte frações precisas do volume indireto entre os perfis do usuário durante a geração automatizada da rotina.
