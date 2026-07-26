# 📋 Regras de Negócio, Arquitetura de UX e Auditoria de Sistema

Este documento detalha o fluxo completo de experiência do usuário (UX), as validações de integridade estrutural e as ferramentas de auditoria e geração automática integradas ao ecossistema do **Transforme Tudo**.

---

## 🗺️ 1. Arquitetura de Navegação e Fluxo do Usuário (UX)

A jornada de criação de treinos foi projetada para equilibrar a liberdade criativa com a rigidez biomecânica através de uma máquina de estados fluida:

* **Centro de Comando (Ponto de Entrada):** Interface unificada que exibe o histórico de evolução recente, o pódio de recordes pessoais (com suporte a *empty states* educativos) e o acesso rápido às fichas ativas.
* **Iniciação da Operação (`WorkoutBuilderStart`):** Tela onde o usuário define o nome do plano (com validação de erros em tempo real), a frequência semanal e a divisão muscular (Split) via carrossel interativo.
* **Configurações Dinâmicas (`AnimatedSize`):** O layout reage organicamente aos parâmetros escolhidos. Frequências elevadas ($\ge 4$ dias) liberam opções avançadas, como a inclusão parametrizada de grupamentos opcionais (Glúteos e Oblíquos).
* **Bifurcação de Geração:**
  * **Modo IA (Automático):** O motor processa as restrições instantaneamente e redireciona o usuário para o sumário executivo.
  * **Modo Manual:** Permite a navegação assistida pelas telas de seleção de grupamentos e perfis biomecânicos.
* **Sumário Executivo (`WorkoutAnalysisReport`):** Apresenta o Equalizador V.E.T. (gráfico comparativo de volume direto vs. sinergia indireta), alertas de otimização de performance (poda de exercícios para proteger o Sistema Nervoso Central) e módulos restritos protegidos por nível administrativo (`AdminStatusService`).
* **Modo de Execução Ativa (`ActiveWorkoutScreen`):** Tela otimizada para o ambiente de treino, permitindo o registro de cargas, controle de séries e gerenciamento de tempo sob tensão.

---

## 🛡️ 2. Validações e Regras de Negócio do Motor

O sistema impõe barreiras estritas para impedir inconsistências anatômicas ou desperdício de volume:

* **Obrigatoriedade de Perfis Biomecânicos:** Nenhuma ficha pode ser persistida se houver lacunas nos perfis estruturais essenciais mapeados para cada grupamento.
* **Prevenção de Redundâncias Cruzadas:** O algoritmo bloqueia a alocação de múltiplos exercícios pertencentes ao exato mesmo perfil biomecânico e grupamento-alvo dentro de uma mesma sessão de treino, prevenindo estresse articular desnecessário.
* **Tratamento de Grupamentos Opcionais:**
  * **Glúteos e Oblíquos:** Só geram metas ativas se ativadas explicitamente pelo usuário ou permitidas pelo Split; caso contrário, operam estritamente como beneficiários de volume indireto.
  * **Músculos Menores (Antebraço e Trapézio):** Possuem regras inteligentes de filtragem visual para evitar poluição na interface, aparecendo apenas quando há sinergia ativa relevante.

---

## ⚖️ 3. O Motor de Distribuição e Ajustes (WEP)

A conversão matemática do volume de treino opera sob pilares determinísticos:

* **Gerenciamento de Volume (SDS - Sets Diretos Semanais):** Metas dinâmicas atreladas diretamente ao número de dias de treino configurados.
* **Abatimento de Séries Indiretas (Sinergia):** Contabiliza o impacto secundário de exercícios compostos em músculos acessórios, somando-os ao volume real do grupamento beneficiado.
* **Convergência para Séries Inteiras:** O motor executa rotinas de arredondamento inteligente e normalização sobre os números decimais resultantes das matrizes de coeficientes, permitindo que o usuário visualize e execute apenas números inteiros de séries.

---

## 🔬 4. Ferramentas de Auditoria e Teste

Para garantir a confiabilidade do produto em ambiente de produção e testes acadêmicos:

* **Camada de Persistência Local/Nuvem (`WorkoutDraftStorage`):** Garante o salvamento seguro de rascunhos e fichas definitivas.
* **Sala de Auditoria Biomecânica (`AdminStatusService`):** Ferramenta exclusiva de desenvolvimento e administração que permite rodar simulações em lote (*Auto-Tester*) do motor, assegurando a robustez matemática das regras de volume e a previsibilidade dos resultados gerados.
