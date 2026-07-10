# Roadmap de Desenvolvimento e Documentação: DeCiDe LAB Website

Este documento registra as etapas de planejamento, arquitetura, design system e implementação do site acadêmico e profissional do **DeCiDe LAB**, hospedado no GitHub Pages em `decide-lab.github.io`.

------------------------------------------------------------------------

## 📅 Cronograma de Execução

### Fase 1: Fundação do Projeto & Ambiente (Atual)

- [X] **Passo 1.1:** Criação da estrutura local de arquivos e diretórios.
- [X] **Passo 1.2:** Configuração do arquivo global do Quarto (`_quarto.yml`) incorporando a identidade visual.
- [X] **Passo 1.3:** Configuração das folhas de estilo customizadas (`styles.css`).
- [X] **Passo 1.4:** Inicialização do repositório Git local e vinculação ao GitHub (`decide-lab.github.io`).

### Fase 2: Desenvolvimento do Core das Páginas (Light/Dark Mode)

- [X] **Passo 2.1:** Implementação da `index.qmd` (Estilo Dashboard/Home).
- [X] **Passo 2.2:** Implementação da `bio.qmd` (Perfil do Laboratório/Membros - Template Trestles).
- [X] **Passo 2.3:** Criação das páginas complementares de UI intensa (`cursos.qmd` e `pesquisa.qmd`).

### Fase 3: Blog, Internacionalização e Publicação

- [X] **Passo 3.1:** Configuração do motor do Blog na pasta `/posts/`.
- [X] **Passo 3.2:** Estruturação da pasta espelhada `/en/` para a versão em inglês.
- [X] **Passo 3.3:** Deployment automatizado no GitHub Pages via GitHub Actions ou CLI do Quarto.

------------------------------------------------------------------------

## 🛠️ Detalhamento Técnico das Etapas Concluídas

### 1. Definição do Brand Kit (Cores Extraídas do Logotipo)

Definimos a identidade visual baseada estritamente no logotipo oficial fornecido. As variáveis serão usadas para sobrescrever os temas padrão do Bootstrap 5 via CSS/SASS: - **Primary (Azul Profundo - Texto DeCiDe):** `#00366E` - **Success (Verde Esmeralda - Célula/LAB):** `#14B74F` - **Warning (Amarelo D Dourado - DNA):** `#FECA28` - **Text Color (Cinza-Escuro - Contornos):** `#1C2B39`


### 2. Configuração Global do Ecossistema (_quarto.yml)
- **O que foi feito:** Criado o esqueleto estrutural de navegação global.
- **Explicação:** Configuramos a inversão de temas nativa do Quarto (`flatly` / `darkly`), amarramos o arquivo `styles.css` para a injeção do Brand Kit e forçamos `title: false` na navbar para blindar o layout contra quebras de linha provocadas por texto concorrendo com a logo. O rodapé foi customizado em HTML inline para garantir que as marcas do laboratório e do framework usem exatamente as cores `#00366E` (Azul Profundo) e `#14B74F` (Verde Esmeralda).
- **Status do Passo 1.2:** 🟢 Concluído.


### 3. Injeção de Identidade Visual Customizada (styles.css)
- **O que foi feito:** Criação da folha de estilos contendo o reset da logo e mapeamento do Brand Kit.
- **Explicação:** Declaramos as cores extraídas do logotipo em variáveis `:root` CSS para facilitar manutenção futura. Implementamos o patch `.navbar-logo` anulando margens, paddings e backgrounds padrão do Quarto que deformavam o posicionamento do logo transparente. Adicionalmente, customizamos os estados ativos de `.btn-primary` e `.nav-pills` para herdar o azul acadêmico (`#00366E`), garantindo consistência visual em componentes iterativos.
- **Status do Passo 1.3:** 🟢 Concluído.

### 4. Governança de Código e Versionamento (Git/.gitignore)
- **O que foi feito:** Criação do `.gitignore` e inicialização do repositório Git alinhado ao branch `main`.
- **Explicação:** Blindamos o repositório contra poluição de metadados de renderização locais isolando as pastas `/.quarto/` e `/_site/`. O fluxo foi preparado para espelhar a estrutura diretamente na organização/usuário `decide-lab` no GitHub, preparando o gatilho automático de hospedagem do GitHub Pages.
- **Status do Passo 1.4:** 🟢 Concluído.

## 2. Atualização da Documentação (`roadmap.md`)

### 5. Criação da Landing Page Estilo Dashboard (index.qmd)
- **O que foi feito:** Codificação da interface inicial responsiva utilizando grids e cards integrados do Bootstrap 5.
- **Explicação:** Aplicamos a Regra Crítica nº 1 envolvendo toda a malha HTML estrutural dentro de blocos de execução dedicados, isolando-a do parser do Pandoc. Os cards de acesso rápido receberam ícones nativos (`bi`) e foram linkados usando URLs puras em conformidade com a Regra nº 2, blindando a navegação contra quebras de rota internas ou erros 404.
- **Status do Passo 2.1:** 🟢 Concluído.

### 6. Implementação da Página Perfil/Bio (bio.qmd)
- **O que foi feito:** Codificação da bio institucional aplicando o template "trestles" integrado com abas dinâmicas do Quarto.
- **Explicação:** Empregamos o template nativo de biografia para organizar metadados e redes sociais em uma barra lateral limpa. Para as Linhas de Pesquisa, implementamos a Regra Crítica nº 3 de Abas Nativas (`::: {.panel-tabset .nav-pills}`), alimentando as seções internas de tags/palavras-chave via blocos HTML isolados, combinando a flexibilidade dos componentes Bootstrap com a estabilidade de navegação do Quarto.
- **Status do Passo 2.2:** 🟢 Concluído.

### 7. Estruturação da Extensão Acadêmica (cursos.qmd)
- **O que foi feito:** Geração da interface de cursos dividida em abas técnicas (computacionais vs bancada) usando Bootstrap 5 estruturado.
- **Explicação:** Respeitando os isolamentos de HTML e links puros, criamos cards informativos contendo marcadores visuais de status (badges de inscrições abertas/esgotadas) e uma tabela responsiva nativa do Bootstrap para exibição de cronogramas complexos de laboratório, facilitando a navegação de alunos e pesquisadores externos interessados.
- **Status do Passo 2.3 (Parte 1):** 🟢 Concluído.

### 8. Vitrine de Divulgação Científica (pesquisa.qmd)
- **O que foi feito:** Geração da página de Linhas de Pesquisa e Projetos Financiados em substituição ao antigo modelo focado em ferramentas.
- **Explicação:** Estruturamos os focos patológicos (Oncologia e Inflamação) usando um grid de cards com bordas acentuadas (`border-start`) nas cores primária e secundária do Brand Kit. Os projetos de fomento receberam cartões limpos contendo metadados técnicos (vigência, número de processo e agência), fornecendo transparência e prestando contas à comunidade acadêmica de forma altamente profissional.
- **Status do Passo 2.3 (Parte 2):** 🟢 Concluído.

### 9. Motor de Listagem e Feed do Blog (posts/index.qmd)
- **O que foi feito:** Configuração do ecossistema de postagens automatizadas do Quarto.
- **Explicação:** Centralizamos na pasta `/posts/` o mecanismo de indexação por metadados. O Quarto foi instruído a organizar os posts por data decrescente, gerando automaticamente barras laterais de categorias e estimativa de tempo de leitura, estabelecendo um canal ágil e limpo de divulgação científica para o laboratório.
- **Status do Passo 3.1:** 🟢 Concluído.

### 10. Arquitetura de Internacionalização (en/ Subfolder)
- **O que foi feito:** Configuração da subpasta `/en/` contendo um `_quarto.yml` local e espelhamento da landing page traduzida.
- **Explicação:** Definimos uma estratégia estável de i18n direcionando o output compilado em inglês para `_site/en`. O seletor de idiomas na navbar chaveia nativamente os caminhos relativos entre as árvores de arquivos em português e inglês sem depender de plugins JavaScript pesados ou quebras de roteamento no servidor estático.
- **Status do Passo 3.2:** 🟢 Concluído.