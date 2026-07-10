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

- [ ] **Passo 2.1:** Implementação da `index.qmd` (Estilo Dashboard/Home).
- [ ] **Passo 2.2:** Implementação da `bio.qmd` (Perfil do Laboratório/Membros - Template Trestles).
- [ ] **Passo 2.3:** Criação das páginas complementares de UI intensa (`cursos.qmd` e `ferramentas.qmd`).

### Fase 3: Blog, Internacionalização e Publicação

- [ ] **Passo 3.1:** Configuração do motor do Blog na pasta `/posts/`.
- [ ] **Passo 3.2:** Estruturação da pasta espelhada `/en/` para a versão em inglês.
- [ ] **Passo 3.3:** Deployment automatizado no GitHub Pages via GitHub Actions ou CLI do Quarto.

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
