
# 🏢 Sistema de Gerenciamento de Vagas de RH

[![React](https://img.shields.io/badge/React-18.3.1-blue.svg)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5.3-blue.svg)](https://typescriptlang.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Lumi%20SDK-green.svg)](https://lumi.new/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3.4.17-blue.svg)](https://tailwindcss.com/)
[![Vite](https://img.shields.io/badge/Vite-5.4.2-purple.svg)](https://vitejs.dev/)

Sistema web moderno e responsivo para gerenciamento completo de vagas de emprego no departamento de recursos humanos. Desenvolvido com React, TypeScript e integração com MongoDB através do Lumi SDK.

## 📋 Índice

- [Características](#características)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Pré-requisitos](#pré-requisitos)
- [Instalação](#instalação)
- [Como Usar](#como-usar)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [API e Banco de Dados](#api-e-banco-de-dados)
- [Scripts Disponíveis](#scripts-disponíveis)
- [Funcionalidades](#funcionalidades)
- [Capturas de Tela](#capturas-de-tela)
- [Contribuição](#contribuição)
- [Deploy](#deploy)
- [Troubleshooting](#troubleshooting)
- [Licença](#licença)

## ✨ Características

- **Interface Moderna**: Design responsivo e intuitivo com Tailwind CSS
- **CRUD Completo**: Criação, visualização, edição e exclusão de vagas
- **Filtros Avançados**: Busca por título, localização, tipo e status
- **Gestão de Status**: Controle de vagas ativas, pausadas e encerradas
- **Detalhes Completos**: Visualização detalhada de cada vaga
- **Notificações**: Feedback em tempo real com toast notifications
- **Responsivo**: Funciona perfeitamente em desktop, tablet e mobile
- **TypeScript**: Código type-safe para maior robustez
- **Performance**: Otimizado com Vite para desenvolvimento rápido

## 🛠️ Tecnologias Utilizadas

### Frontend
- **React 18.3.1** - Biblioteca para interfaces de usuário
- **TypeScript 5.5.3** - Superset tipado do JavaScript
- **React Router DOM 6.26.0** - Roteamento para SPA
- **Tailwind CSS 3.4.17** - Framework CSS utilitário
- **Lucide React 0.540.0** - Ícones modernos
- **React Hot Toast 2.4.1** - Notificações elegantes

### Backend & Banco de Dados
- **Lumi SDK 0.1.5** - SDK para integração com MongoDB
- **MongoDB** - Banco de dados NoSQL
- **Vite 5.4.2** - Build tool e dev server

### Desenvolvimento
- **ESLint** - Linting de código
- **PostCSS** - Processamento de CSS
- **Autoprefixer** - Prefixos CSS automáticos

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- **Node.js** (versão 18 ou superior)
- **npm** ou **yarn**
- **Git** para controle de versão
- Acesso à internet para integração com Lumi SDK



### 1. Clone o repositório
```bash
git clone https://github.com/seu-usuario/sistema-vagas-rh.git
cd sistema-vagas-rh
```

### 2. Instale as dependências
```bash
npm install
# ou
yarn install
```

### 3. Configure o ambiente
O projeto utiliza o Lumi SDK que já está configurado no arquivo `src/lib/lumi.ts`. Não é necessária configuração adicional.

### 4. Inicie o servidor de desenvolvimento
```bash
npm run dev
# ou
yarn dev
```
### 5. Acesse a aplicação
Abra seu navegador e acesse: `(https://hr-vacancy-manager.lumi.ing)`

## 🎯 Como Usar

### Navegação Principal
- **Lista de Vagas**: Página inicial com todas as vagas cadastradas
- **Criar Vaga**: Formulário para cadastrar nova vaga
- **Detalhes**: Visualização completa de uma vaga específica
- **Editar**: Modificação de vagas existentes

### Operações Básicas

#### Criar Nova Vaga
1. Clique em "Criar Nova Vaga" na página principal
2. Preencha todos os campos obrigatórios:
   - Título da vaga
   - Empresa
   - Localização
   - Tipo (Presencial, Remoto, Híbrido)
   - Nível (Júnior, Pleno, Sênior)
   - Salário
   - Descrição
3. Clique em "Criar Vaga"

#### Filtrar Vagas
- Use a barra de busca para filtrar por título
- Selecione filtros de localização, tipo e status
- Os resultados são atualizados automaticamente

#### Editar Vaga
1. Na lista de vagas, clique em "Editar" na vaga desejada
2. Modifique os campos necessários
3. Clique em "Salvar Alterações"

#### Excluir Vaga
1. Na lista de vagas, clique em "Excluir"
2. Confirme a ação no modal de confirmação

## 📁 Estrutura do Projeto

```
sistema-vagas-rh/
├── public/                    # Arquivos públicos
├── src/                       # Código fonte
│   ├── components/           # Componentes React
│   │   └── Layout.tsx       # Layout principal da aplicação
│   ├── entities/            # Esquemas MongoDB
│   │   └── vagas.json      # Schema das vagas
│   ├── hooks/               # Hooks customizados
│   │   └── useVagas.ts     # Hook para operações CRUD
│   ├── lib/                 # Configurações
│   │   └── lumi.ts         # Cliente Lumi SDK
│   ├── pages/               # Páginas da aplicação
│   │   ├── CriarVaga.tsx   # Página de criação
│   │   ├── DetalhesVaga.tsx # Página de detalhes
│   │   ├── EditarVaga.tsx  # Página de edição
│   │   └── ListaVagas.tsx  # Página principal
│   ├── App.tsx              # Componente raiz
│   ├── index.css           # Estilos globais
│   ├── main.tsx            # Ponto de entrada
│   └── vite-env.d.ts       # Tipos do Vite
├── index.html               # Template HTML
├── package.json            # Dependências e scripts
├── tailwind.config.js      # Configuração Tailwind
├── tsconfig.json           # Configuração TypeScript
└── vite.config.ts          # Configuração Vite
```

## 🗄️ API e Banco de Dados

### Schema da Vaga (MongoDB)
```json
{
  "titulo": "string",           // Título da vaga
  "empresa": "string",          // Nome da empresa
  "localizacao": "string",      // Localização da vaga
  "tipo": "string",            // Presencial/Remoto/Híbrido
  "nivel": "string",           // Júnior/Pleno/Sênior
  "salario": "string",         // Faixa salarial
  "descricao": "string",       // Descrição detalhada
  "status": "string",          // ativa/pausada/encerrada
  "criadoEm": "string",        // Data de criação (ISO)
  "atualizadoEm": "string"     // Data de atualização (ISO)
}
```

### Operações CRUD via Lumi SDK
```typescript
// Listar vagas
const { list } = await lumi.entities.vagas.list()

// Criar vaga
await lumi.entities.vagas.create(dadosVaga)

// Obter vaga por ID
const vaga = await lumi.entities.vagas.get(id)

// Atualizar vaga
await lumi.entities.vagas.update(id, dadosAtualizados)

// Excluir vaga
await lumi.entities.vagas.delete(id)
```

## 📜 Scripts Disponíveis

```bash
# Desenvolvimento
npm run dev          # Inicia servidor de desenvolvimento

# Build
npm run build        # Gera build de produção

# Preview
npm run preview      # Visualiza build de produção

# Linting
npm run lint         # Executa verificação de código
```

## 🔧 Funcionalidades

### ✅ Implementadas
- [x] Listagem de vagas com paginação
- [x] Criação de novas vagas
- [x] Edição de vagas existentes
- [x] Exclusão de vagas
- [x] Visualização detalhada
- [x] Filtros por título, localização, tipo e status
- [x] Design responsivo
- [x] Notificações de sucesso/erro
- [x] Validação de formulários
- [x] Integração com MongoDB via Lumi SDK

### 🔄 Melhorias Futuras
- [ ] Autenticação de usuários
- [ ] Permissões por nível de acesso
- [ ] Upload de anexos (CV, cartas)
- [ ] Dashboard com estatísticas
- [ ] Exportação de relatórios
- [ ] Notificações por email
- [ ] API REST para integrações
- [ ] Testes automatizados



## 🚀 Deploy

### Build de Produção
```bash
npm run build
```

### Deploy com Vercel
```bash
npm install -g vercel
vercel --prod
```

### Deploy com Netlify
```bash
npm run build
# Upload da pasta dist/ para Netlify
```

### Variáveis de Ambiente
O projeto utiliza o Lumi SDK que não requer configuração adicional de ambiente.

## 🔧 Troubleshooting

### Problemas Comuns

#### Erro de dependências
```bash
# Limpe o cache e reinstale
rm -rf node_modules package-lock.json
npm install
```

#### Erro de build
```bash
# Verifique tipos TypeScript
npm run lint
```

#### Erro de conexão com banco
- Verifique se o Lumi SDK está configurado corretamente
- Confirme se há conexão com internet
- Verifique logs no console do navegador

#### Performance lenta
- Use `npm run build` para versão otimizada
- Verifique se há muitos dados sendo carregados
- Implemente paginação se necessário

### Logs e Debug
- Abra DevTools (F12) para ver logs
- Verifique Network tab para requisições
- Use React DevTools para debug de componentes


