# 🏋️ Meu Treino — Workout Tracker

Aplicativo PWA para criação, execução e acompanhamento de treinos de academia — ideal para quem treina em casa, na academia do condomínio ou em qualquer lugar com equipamentos básicos (Smith, polias, barra fixa e solo).

## Funcionalidades

### Treinar
- Execução guiada do treino diário com checklist de séries
- Registro de carga (kg) por série
- Timer de descanso configurável (45s, 60s, 75s, 90s, 120s) com vibração ao finalizar
- Barra de progresso por dia e indicadores visuais de conclusão
- Controle de semanas com contagem de semanas completas
- Aquecimento e cardio sugeridos por dia
- Ações rápidas: reiniciar dia, iniciar nova semana e zerar tudo

### Banco de Exercícios
- **29 exercícios** pré-cadastrados organizados em **11 grupos musculares**: Peito, Costas, Ombro, Bíceps, Tríceps, Quadríceps, Posterior, Glúteo, Panturrilha, Core e Corpo Inteiro
- Cada exercício inclui: nome, grupo muscular, equipamento, dica de execução, séries/reps/descanso padrão
- Busca por nome e filtro por grupo muscular
- CRUD completo — crie, edite e exclua exercícios personalizados

### Montar Treino
- Criação e edição de dias de treino com nome, subtítulo, aquecimento e cardio
- Adicionar exercícios do banco ao dia de treino
- Personalizar séries, repetições e descanso por exercício em cada dia
- **Drag & drop** para reordenar exercícios dentro do dia
- Adicionar e remover dias de treino

### Acompanhamento Corporal
- Registro de medidas: peso, altura, % gordura, % massa muscular
- Circunferências: cintura, peito, braço D/E, coxa D/E, quadril, panturrilha
- **Deltas automáticos** entre o registro atual e o anterior (com indicação visual positiva/negativa)
- Histórico completo com opção de exclusão individual

## Treino Padrão

O app vem com uma divisão **Push/Pull/Legs** de 5 dias pré-configurada:

| Dia | Nome | Foco |
|-----|------|------|
| D1 | Push A | Peito · Ombro · Tríceps |
| D2 | Pull A | Costas · Bíceps |
| D3 | Legs | Quadríceps · Posterior · Glúteo |
| D4 | Push B | Ombro · Tríceps · Peito |
| D5 | Pull B + Core | Costas · Bíceps · Abdome |

## Tecnologias

| Tecnologia | Uso |
|------------|-----|
| **React 18** | UI reativa (carregado via CDN) |
| **Babel Standalone** | Transpilação JSX no browser |
| **LocalStorage** | Persistência de dados (prefixo `gym_`) |
| **Service Worker** | Cache offline (estratégia cache-first) |
| **Web App Manifest** | Instalação como PWA |
| **Google Fonts** | Bebas Neue (títulos) + DM Sans (corpo) |

## Estrutura do Projeto

```
app-meu-treino/
├── index.html      # Aplicação completa (HTML + CSS + React)
├── sw.js           # Service Worker para funcionamento offline
├── manifest.json   # Manifesto PWA (nome, ícone, tema)
└── README.md
```

> **Arquitetura single-file:** todo o código (estilos, componentes React e lógica) está contido em `index.html`. Não há etapa de build — basta abrir o arquivo ou servir com qualquer servidor estático.

## Como Usar

### Opção 1 — Abrir diretamente
Abra o arquivo `index.html` no navegador (algumas funcionalidades do Service Worker podem exigir HTTPS ou localhost).

### Opção 2 — Servidor local
```bash
# Com Python
python -m http.server 8000

# Com Node.js (npx)
npx serve .

# Com VS Code
# Instale a extensão "Live Server" e clique em "Go Live"
```

Acesse `http://localhost:8000` e pronto.

### Instalar como App (PWA)
No Chrome/Edge, clique no ícone de instalação na barra de endereço ou vá em **⋮ → Instalar aplicativo**. O app funciona offline após a primeira carga.

## Armazenamento de Dados

Todos os dados são salvos **localmente no navegador** via `localStorage`. Não há backend nem envio de dados para servidores externos. Para limpar todos os dados, use o botão 🗑️ na tela de treino ou limpe o armazenamento do site pelo navegador.

## Personalização

- **Exercícios:** adicione, edite ou remova exercícios pelo Banco de Exercícios
- **Treinos:** monte sua própria divisão de treino na tela Montar
- **Medidas:** acompanhe a evolução corporal com registros periódicos

## Licença

Projeto pessoal de uso livre.
