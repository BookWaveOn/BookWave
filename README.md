# 📖 BookWave - Sistema de Locadora de Livros Online

Bem-vindo ao projeto da **BookWave**, uma locadora de livros online que proporciona uma experiência simples, prática e eficiente para os amantes da leitura.

Este documento contém todas as **regras de negócio** necessárias para o desenvolvimento do sistema.

---

## 🎯 Objetivo

Permitir que usuários possam:
- Navegar no catálogo de livros disponíveis.
- Alugar livros físicos ou digitais.
- Acompanhar seus aluguéis.
- Avaliar livros.
- Administradores possam gerenciar o acervo e as locações.

---

## 🔥 Funcionalidades Principais

- Cadastro e login de usuários.
- Catálogo de livros com filtros e pesquisa.
- Visualização de detalhes do livro.
- Aluguel de livros com controle de disponibilidade.
- Área do usuário para gerenciar seus aluguéis.
- Administração do catálogo e controle de devoluções.

---

## 🧩 Fluxo Geral do Sistema

1. **Página Inicial**  
   Exibe destaque de livros e acesso ao catálogo.

2. **Cadastro/Login de Usuários**  
   - Cadastro de novos usuários com dados obrigatórios: Nome, Email, Telefone, Endereço, Data de Nascimento e Senha.
   - Login de usuários registrados.
   - Recuperação de senha.

3. **Catálogo de Livros**
   - Listagem de livros disponíveis com opção de filtrar e buscar.
   - Exibição de capa, título, autor e status de disponibilidade.
   - Botão para iniciar aluguel.

4. **Detalhe de Livro**
   - Exibe informações completas: capa, nome, autor, tipo (físico/digital), disponibilidade e nota de avaliação.
   - Botão para alugar livro.

5. **Processo de Aluguel**
   - Confirmação do aluguel.
   - Aplicação de regras:
     - Prazo padrão de aluguel: **15 dias**.
     - Permite **1 renovação** por livro alugado.
     - Caso o prazo expire, o usuário deve **pagar multa** antes de novo aluguel.

6. **Área do Usuário**
   - Visualizar todos os livros alugados.
   - Ver prazos e status de aluguel.
   - Renovar aluguel (uma vez por livro).
   - Devolver livro.
   - Pagar multa se aplicável.
   - Avaliar livros alugados.

7. **Administração (restrita a usuários administradores)**
   - Login administrativo separado.
   - Cadastro de novos livros no catálogo (nome, autor, tipo, gênero, imagem de capa).
   - Listagem e gerenciamento dos aluguéis em andamento.
   - Confirmação de devoluções de livros.

---

## 🛡️ Regras de Negócio

- Um livro só pode ser alugado se estiver **disponível**.
- Um usuário pode ter **vários livros alugados** simultaneamente, desde que sem pendências (multa ou devolução atrasada).
- Cada aluguel:
  - Dura **15 dias** inicialmente.
  - Pode ser **renovado uma única vez** por mais **15 dias**.
- Após vencimento do prazo:
  - Usuário deve pagar multa para continuar alugando.
- Livro alugado deve mudar seu status para **indisponível** no catálogo.
- Administradores podem:
  - Confirmar devoluções e tornar livros disponíveis novamente.
  - Cadastrar e editar informações dos livros.
- Sistema deve manter **histórico de avaliações** dos livros.

---

## 📄 Estrutura Básica de Telas

- Página Inicial
- Tela de Login/Cadastro
- Catálogo de Livros
- Página de Detalhe de Livro
- Página de Aluguel
- Área do Usuário (Meus Aluguéis / Minhas Avaliações)
- Área do Administrador (Painel de Controle)

---

## ✍️ Observações Finais

- O sistema deverá ser responsivo para funcionar em desktop e dispositivos móveis.
- Interface focada em usabilidade simples e direta.
- Priorizar a segurança dos dados dos usuários (como senha criptografada).

---

# 📚 BookWave
_"Leia onde quiser, quando quiser!"_


# 🛤️ Fluxo de Telas
[Início] 
   ↓
[Página Inicial] → [Login] → [Página Principal (Usuário)]
                            ↘︎
                             [Catálogo] → [Detalhes do Livro] → [Confirmar Aluguel]
                            ↘︎
                             [Meus Aluguéis] → [Renovar / Devolver / Avaliar]
                            ↘︎
                             [Área Administrativa]


# 🎨 Protótipo Visual Simples (Wireframe)

[BookWave Logo]    [Login] [Cadastro]

---
| 📚 Destaques do Catálogo |
| Livro 1 | Livro 2 | Livro 3 |
---

<svg width="800" height="600" xmlns="http://www.w3.org/2000/svg">
  <style>
    .box { fill: #f9f9f9; stroke: #333; stroke-width: 2; }
    .text { font: bold 14px sans-serif; fill: #333; }
    .arrow { stroke: #333; stroke-width: 2; marker-end: url(#arrowhead); }
  </style>

  <defs>
    <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#333" />
    </marker>
  </defs>

  <!-- Boxes -->
  <rect class="box" x="300" y="20" width="200" height="40" />
  <rect class="box" x="300" y="100" width="200" height="40" />
  <rect class="box" x="100" y="200" width="200" height="40" />
  <rect class="box" x="500" y="200" width="200" height="40" />
  <rect class="box" x="300" y="300" width="200" height="40" />
  <rect class="box" x="300" y="400" width="200" height="40" />
  <rect class="box" x="100" y="500" width="200" height="40" />
  <rect class="box" x="500" y="500" width="200" height="40" />

  <!-- Texts -->
  <text class="text" x="330" y="45">Página Inicial</text>
  <text class="text" x="370" y="125">Login</text>
  <text class="text" x="140" y="225">Catálogo</text>
  <text class="text" x="540" y="225">Meus Aluguéis</text>
  <text class="text" x="340" y="325">Detalhe do Livro</text>
  <text class="text" x="340" y="425">Área Administrativa</text>
  <text class="text" x="140" y="525">Alugar Livro</text>
  <text class="text" x="540" y="525">Avaliar Livro</text>

  <!-- Arrows -->
  <line class="arrow" x1="400" y1="60" x2="400" y2="100" />
  <line class="arrow" x1="400" y1="140" x2="200" y2="200" />
  <line class="arrow" x1="400" y1="140" x2="600" y2="200" />
  <line class="arrow" x1="200" y1="240" x2="400" y2="300" />
  <line class="arrow" x1="600" y1="240" x2="400" y2="300" />
  <line class="arrow" x1="400" y1="340" x2="400" y2="400" />
  <line class="arrow" x1="400" y1="440" x2="200" y2="500" />
  <line class="arrow" x1="400" y1="440" x2="600" y2="500" />
</svg>

