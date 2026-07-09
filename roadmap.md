# Roadmap de Desenvolvimento e Documentação: DeCiDe LAB Website

Este documento registra as etapas de planejamento, arquitetura, design system e implementação do site acadêmico e profissional do **DeCiDe LAB**, hospedado no GitHub Pages em `decide-lab.github.io`.

---

## 📅 Cronograma de Execução

### Fase 1: Fundação do Projeto & Ambiente (Atual)
- [ ] **Passo 1.1:** Criação da estrutura local de arquivos e diretórios.
- [ ] **Passo 1.2:** Configuração do arquivo global do Quarto (`_quarto.yml`) incorporando a identidade visual.
- [ ] **Passo 1.3:** Configuração das folhas de estilo customizadas (`styles.css`).
- [ ] **Passo 1.4:** Inicialização do repositório Git local e vinculação ao GitHub (`decide-lab.github.io`).

### Fase 2: Desenvolvimento do Core das Páginas (Light/Dark Mode)
- [ ] **Passo 2.1:** Implementação da `index.qmd` (Estilo Dashboard/Home).
- [ ] **Passo 2.2:** Implementação da `bio.qmd` (Perfil do Laboratório/Membros - Template Trestles).
- [ ] **Passo 2.3:** Criação das páginas complementares de UI intensa (`cursos.qmd` e `ferramentas.qmd`).

### Fase 3: Blog, Internacionalização e Publicação
- [ ] **Passo 3.1:** Configuração do motor do Blog na pasta `/posts/`.
- [ ] **Passo 3.2:** Estruturação da pasta espelhada `/en/` para a versão em inglês.
- [ ] **Passo 3.3:** Deployment automatizado no GitHub Pages via GitHub Actions ou CLI do Quarto.

---

## 🛠️ Detalhamento Técnico das Etapas Concluídas

### 1. Definição do Brand Kit (Cores Extraídas do Logotipo)
Definimos a identidade visual baseada estritamente no logotipo oficial fornecido. As variáveis serão usadas para sobrescrever os temas padrão do Bootstrap 5 via CSS/SASS:
- **Primary (Azul Profundo - Texto DeCiDe):** `#00366E`
- **Success (Verde Esmeralda - Célula/LAB):** `#14B74F`
- **Warning (Amarelo D Dourado - DNA):** `#FECA28`
- **Text Color (Cinza-Escuro - Contornos):** `#1C2B39`