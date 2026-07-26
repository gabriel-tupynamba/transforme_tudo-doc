# 🗄️ Arquitetura de Software e Modelagem de Dados (NoSQL)

Este documento detalha as decisões de arquitetura e a modelagem do banco de dados (Firebase Firestore) que sustentam o **Transforme Tudo**.

A premissa arquitetural do aplicativo é a **Otimização de Leitura (Read-Optimized Data Model)**. Em vez de calcular as complexas matrizes de intersecção biomecânica em tempo de execução (*runtime*), o sistema processa e salva os coeficientes fracionados de **Equivalência de Série** ($S_e$) estaticamente nos documentos do banco de dados. Isso garante complexidade de leitura $O(1)$, maximizando a fluidez da interface no Flutter e minimizando o consumo de bateria e dados do dispositivo móvel.

---

## 🏗️ Topologia das Coleções Principais

O motor biomecânico é alimentado por três coleções principais, estruturadas de forma hierárquica e relacionadas por IDs (Foreign Keys lógicas).

## 1. Coleção `muscle_groups`

Gerencia a taxonomia macroscópica do corpo humano. Define quais grupos são obrigatórios na construção de uma rotina e controla a renderização da interface.

```json
{
  "id": "peitoral",
  "name": "Peitoral",
  "mandatory": true,
  "hasOptionalProfiles": false,
  "order": 1
}
```

> **Nota de Engenharia:** A propriedade `mandatory` dita o comportamento do Motor de Prescrição, impedindo que o algoritmo de montagem gere uma rotina (como *Full Body*) que deixe de fora um grupamento essencial.

---

## 2. Coleção `profiles`

Cada grupo muscular possui o seu próprio documento de Divisões Biomecânicas (Perfis). Esta coleção traduz a anatomia funcional em regras computacionais.

```json
{
  "id": "peitoral_p1",
  "muscleId": "peitoral",
  "name": "Empurrar horizontal",
  "focus": "Peitoral Completo",
  "mechanics": "Braços alinhados ao plano do tronco",
  "mandatory": true,
  "profileIndex": 1,
  "imagePath": "https://url_da_imagem..."
}
```

> **Nota de Engenharia:** A vinculação de `muscleId` cria o escopo de busca. O sistema garante que, para validar o treino de Peitoral, o usuário ou o algoritmo precisem preencher os requisitos de todos os perfis marcados como `mandatory: true`.

---

## 3. Coleção `exercises` *(O Núcleo de Dados)*

Esta é a coleção mais densa do sistema. Ela não apenas guarda os metadados do exercício, mas também carrega o banco de variações (mais de 300 cadastradas), contendo os coeficientes exatos pré-calculados pelo Sistema de Auditoria de Carga (SAC 6.5) e propriedades utilizadas pela interface.

```json
{
  "id": "supino_reto",
  "name": "Supino Reto",
  "musclePrimary": "peitoral",
  "profileId": "peitoral_p1",
  "isCompound": true,
  "tags": ["barra", "halter", "maquina", "cabo"],
  "coefficients": {
    "peitoral": { "p1": 0.8 },
    "triceps": { "p1": 0.45 },
    "ombros": { "p1": 0.3 }
  },
  "variations": [
    {
      "type": "Barra",
      "slug": "Barbell_Bench_Press_-_Medium_Grip",
      "tier": 3,
      "isCommon": true,
      "coefficients": {
        "peitoral": { "p1": 0.8 },
        "triceps": { "p1": 0.45 },
        "ombros": { "p1": 0.3 }
      },
      "alignX": 0.0,
      "alignY": -0.4345
    },
    {
      "type": "Máquina Articulada",
      "slug": "Leverage_Chest_Press",
      "tier": 3,
      "isCommon": true,
      "coefficients": {
        "peitoral": { "p1": 1.0 },
        "triceps": { "p1": 0.6 },
        "ombros": { "p1": 0.45 }
      },
      "alignX": 0.0,
      "alignY": 0.0
    }
  ]
}
```

---

# 🚀 Justificativa Técnica do Modelo *(Design Patterns)*

### Desnormalização Inteligente

As matrizes de coeficientes são declaradas dentro de cada variação. Isso permite que um **Supino Reto** genérico entregue um vetor de estímulo, enquanto a variação **Máquina Articulada** entregue vetores independentes, aumentando a carga sobre o peitoral de **0.8** para **1.0** devido à estabilidade sistêmica.

### Integração Backend–UI

Os atributos `alignX`, `alignY`, `slug` e `tier` eliminam a necessidade de configurações visuais locais no Flutter. O posicionamento de imagens, a prioridade de exibição (`tier`) e a integração com catálogos de animações ou vídeos (`slug`) são resolvidos nativamente na consulta ao banco de dados.

### Escalabilidade Sem Servidor (*Serverless*)

Toda a inteligência biomecânica está persistida no banco de dados. O aplicativo não exige capacidade massiva de processamento centralizado, tornando a arquitetura altamente resiliente a perdas momentâneas de rede e a picos de acesso.
