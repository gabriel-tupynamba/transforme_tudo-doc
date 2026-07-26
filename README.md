# 🚀 Transforme Tudo

> **Motor Biomecânico Avançado e Plataforma Mobile de Prescrição Inteligente de Treinos**

O **Transforme Tudo** é uma solução mobile de alta performance desenvolvida em **Flutter** e integrada ao **Firebase (NoSQL)**, projetada para resolver um problema crônico na musculação: a prescrição genérica de treinos baseada em "achismos" ou volume cego. O sistema aplica rigor científico e engenharia determinística para calcular a real **transferência de tensão mecânica** aos grupos musculares.

---

## 🏛️ Documentação Técnica Oficial

A arquitetura, a matemática e as regras de negócio do sistema estão parcialmente detalhadas na pasta `/docs`:

* **[Arquitetura e Banco de Dados (`docs/arquitetura_e_banco_de_dados.md`)](docs/arquitetura_e_banco_de_dados.md)** — Topologia NoSQL otimizada para leitura ($O(1)$), estrutura de coleções (`muscle_groups`, `profiles`, `exercises`) e desacoplamento de UI/Dados.
* **[Motor Biomecânico e SAC 6.5 (`docs/motor_biomecanico_sac_6_5.md`)](docs/motor_biomecanico_sac_6_5.md)** — Sistema de Auditoria de Carga, critérios binários ($C1$ a $C6$) de estabilidade sistêmica/vetorial e o modelo de Equivalência de Série ($S_e$).
* **[Algoritmo de Prescrição / Motor Cascata 2.0 (`docs/algoritmo_de_prescricao_wep.md`)](docs/algoritmo_de_prescricao_wep.md)** — WEP (*Volume Equilibrium Engine*), iterações de convergência para séries inteiras e abatimento inteligente de volume indireto.
* **[Regras de Negócio, UX e Auditoria (`docs/regras_de_negocio_e_fluxos.md`)](docs/regras_de_negocio_e_fluxos.md)** — Máquina de estados de navegação, prevenção de redundâncias cruzadas, parsing inteligente de variações ("Corte de Espada") e o Equalizador V.E.T.

---

## ⚙️ Principais Diferenciais de Engenharia

1. **Read-Optimized Data Model:** Todo o processamento pesado e as matrizes complexas de coeficientes biomecânicos foram pré-calculados e persistidos estaticamente. O aplicativo executa leituras leves sem sobrecarregar o *runtime* do dispositivo móvel.
2. **Motor Cascata 2.0:** Algoritmo de convergência matemática que gerencia o balanço entre volume direto e sinergias indiretas (músculos acessórios como tríceps, antebraço e glúteos), normalizando frações decimais em séries inteiras exatas para a execução prática.
3. **Gestão Dinâmica de Grupos Opcionais e Poda (*Pruning*):** O sistema oculta automaticamente exercícios de isolamento quando a meta do grupamento opcional (ex: glúteos) já foi integralmente atingida pelo volume indireto dos compostos, prevenindo *overtraining* e aliviando a interface (desligando metas de grupos inativos para evitar falsas sensações de fracasso).
4. **Parsing de Variações ("Corte de Espada"):** Mecanismo de tratamento de strings baseado em delimitadores que separa a base do exercício de sua variação específica (ex: `SUPINO RETO | BARRA`), garantindo flexibilidade nos coeficientes dinâmicos sem poluir o histórico ou o pódio de recordes do usuário.

---

## 🛠️ Stack Tecnológica

* **Frontend:** Flutter (Dart), reatividade baseada em estados otimizados, componentes fluidos (`AnimatedSize`) e layouts responsivos voltados para a usabilidade em ambiente de academia.
* **Backend / Persistência:** Firebase Firestore (NoSQL), modelagem orientada a documentos aninhados, camada de persistência local/nuvem (`WorkoutDraftStorage`) e ferramentas exclusivas de auditoria em lote para desenvolvedores (`AdminStatusService`).

---
<div align="center">
  <sub>Desenvolvido com rigor acadêmico e excelência em engenharia de software.</sub>
</div>
