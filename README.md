# 🚀 Transforme Tudo

> **Ecossistema Mobile Avançado de Desenvolvimento Pessoal, Gestão de Treinamento Biomecânico e Produtividade**

O **Transforme Tudo** é uma solução mobile robusta e de alta performance desenvolvida em **Flutter**, estruturada com arquitetura orientada a microsserviços frontend e integrada ao ecossistema **Firebase (NoSQL)**. O aplicativo vai muito além de uma simples ferramenta de treino: ele integra serviços de execução em segundo plano, sobreposições flutuantes (*bubble overlays*), player multimídia nativo, gráficos analíticos complexos e um motor determinístico de prescrição de treinos baseado na biomecânica da tensão mecânica.

---

## 🚀 Acesse o Protótipo

Teste o Transforme Tudo através do navegador, baixe a build compilada para Android ou assista ao vídeo de apresentação da arquitetura:

* 🌐 **Acesso Web (PWA):** [Clique aqui para acessar o Transforme Tudo](COLOQUE_SEU_LINK_DO_FIREBASE_AQUI.web.app)
* 📱 **Download Android (APK):** [Baixar TransformeTudo.apk](./TransformeTudo.apk)
* 🎬 **Vídeo de Apresentação:** *Ainda não disponível — Link em breve*

### 🗝️ Acesso Demonstrativo para Avaliação
Para testes operacionais rápidos na build de demonstração, utilize as credenciais padrão de auditoria:
* **Usuário:** `ContaTeste`
* **Senha:** `testando`

---

## 🏛️ Documentação Técnica Oficial (`/docs`)

A arquitetura, a matemática e as regras de negócio do sistema estão detalhadas nos módulos da pasta `/docs`:

* **[Arquitetura e Banco de Dados (`docs/arquitetura_e_banco_de_dados.md`)](docs/arquitetura_e_banco_de_dados.md)** — Topologia NoSQL otimizada para leitura ($O(1)$), estrutura de coleções (`muscle_groups`, `profiles`, `exercises`) e desacoplamento de UI/Dados.
* **[Motor Biomecânico e SAC 6.5 (`docs/motor_biomecanico_sac_6_5.md`)](docs/motor_biomecanico_sac_6_5.md)** — Sistema de Auditoria de Carga, critérios binários ($C1$ a $C6$) de estabilidade sistêmica/vetorial e o modelo de Equivalência de Série ($S_e$).
* **[Algoritmo de Prescrição / Motor Cascata 2.0 (`docs/algoritmo_de_prescricao_wep.md`)](docs/algoritmo_de_prescricao_wep.md)** — WEP (*Volume Equilibrium Engine*), iterações de convergência para séries inteiras e abatimento inteligente de volume indireto em grupamentos sinergistas.
* **[Regras de Negócio, UX e Auditoria (`docs/regras_de_negocio_e_fluxos.md`)](docs/regras_de_negocio_e_fluxos.md)** — Máquina de estados de navegação, prevenção de redundâncias cruzadas, parsing inteligente de variações ("Corte de Espada") e o Equalizador V.E.T.

---

## ⚙️ Principais Diferenciais de Engenharia e Produto

1. **Read-Optimized Data Model:** Todo o processamento pesado e as matrizes complexas de coeficientes biomecânicos foram pré-calculados e persistidos estaticamente no Firebase. O aplicativo executa leituras leves sem sobrecarregar o *runtime* do dispositivo móvel.
2. **Motor Cascata 2.0:** Algoritmo de convergência matemática que gerencia o balanço entre volume direto e sinergias indiretas (como o impacto mecânico cruzado em grupamentos primários e secundários), normalizando frações decimais em séries inteiras exatas para a execução prática.
3. **Gestão Dinâmica de Grupos Opcionais e Poda (*Pruning*):** O sistema oculta automaticamente exercícios de isolamento quando a meta do grupamento opcional (ex: glúteos) já foi integralmente atingida pelo volume indireto dos compostos, prevenindo *overtraining* e aliviando a interface (desligando metas de grupos inativos para evitar falsas sensações de fracasso).
4. **Parsing de Variações ("Corte de Espada"):** Mecanismo de tratamento de strings baseado em delimitadores que separa a base do exercício de sua variação específica (ex: `SUPINO RETO | BARRA`), garantindo flexibilidade nos coeficientes dinâmicos sem poluir o histórico ou o pódio de recordes do usuário.
5. **Execução Nativa em Segundo Plano e Overlays:** Integração profunda com o sistema operacional para rodar tarefas contínuas via *Foreground Tasks* e renderização de janelas flutuantes (*Bubble Overlays*), permitindo controle ativo de tempo e sessões sem fricção.

---

## 🛠️ Stack Tecnológica e Ecossistema de Dependências

O projeto consome um conjunto maduro de pacotes do ecossistema Flutter para entregar uma experiência nativa de nível industrial:

* **Core & Backend:** `firebase_core`, `firebase_auth`, `cloud_firestore` (Persistência NoSQL e autenticação).
* **Serviços Nativos & Background:** `flutter_foreground_task`, `flutter_overlay_window` (Modo bolha flutuante e tarefas contínuas), `wakelock_plus` (Prevenção de suspensão de tela durante os treinos).
* **Mídia & UI Multimedia:** `youtube_player_flutter`, `just_audio` (Reprodução de tutoriais e suporte a áudio), `cached_network_image` / `flutter_cache_manager` (Gestão de cache de assets e imagens em WebP).
* **Produtividade & Análise:** `table_calendar` (Gestão de calendário e frequência), `fl_chart` (Renderização de gráficos analíticos de desempenho), `screenshot` & `share_plus` (Exportação e compartilhamento de relatórios e fichas).
* **Utilitários de Sistema:** `connectivity_plus`, `shared_preferences`, `path_provider`, `intl`, `flutter_dotenv`, `flutter_svg`, `flutter_native_splash`.

---
<div align="center">
  <sub>Desenvolvido com rigor acadêmico, arquitetura modular avançada e excelência em engenharia de software.</sub>
</div>
