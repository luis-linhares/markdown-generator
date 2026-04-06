---
name: markdown-generator
description: >
  Use this skill whenever the user asks to generate, convert, or format any input (like free text, URLs, images, or files) into markdown files (.md). Also triggers if the user asks for summaries saved as markdown, extracting action items to markdown, or formatting notes for repositories (like Github READMEs). This skill enforces a structured flow: it interviews the user to determine the summary type (or identical conversion), the number of output files, and the output directory. It strictly requires showing a preview of the file structure and topic outlines BEFORE actually generating any markdown files.
---

# Markdown Generator Skill

This skill handles the ingestion of different types of content (text, files, URLs, images) and orchestrates the creation of structured Markdown files.

## Workflow

When the user triggers this skill, you MUST follow these steps strictly and in order. Do NOT skip steps and do NOT generate the final files until Step 4.

### Step 1: Ingestion & Interview
Acknowledge the inputs provided by the user. If they haven't provided any input yet, ask for it.
Ask the following questions to understand how they want the content formatted:

1. **Qual tipo de conteúdo final você deseja?** (Peça para escolher pelo número)
   - [0] **Cópia Idêntica:** Manter o conteúdo original exatamente como está, apenas formatado para Markdown.
   - [1] **Resumo Executivo (Executive Summary):** Uma visão geral de alto nível dos conceitos principais.
   - [2] **Pontos-Chave (Bullet Points):** Uma lista direta com os fatos, dados ou argumentos mais importantes.
   - [3] **Itens de Ação (Action Items):** Foco no que precisa ser feito (útil para atas, reuniões, etc).
   - [4] **Síntese Temática:** Agrupamento de informações por tópicos principais (excelente para múltiplas fontes).
   - [5] **Personalizado:** O usuário informa exatamente o que quer extrair ou focar.

2. **Como devemos organizar os arquivos?** 
   - A saída deve ser feita em um único arquivo `.md`, ou dividida em múltiplos arquivos?

3. **Onde devo salvar os arquivos?**
   - Sugira o diretório padrão: `docs/markdown-generator/{nome-sugerido}/` (onde `{nome-sugerido}` é um resumo hifenizado de até 3 palavras sobre o conteúdo). Peça a confirmação ou pergunte se querem alterar o caminho.

### Step 2: Content Analysis & Topic Structure Generation
Wait for the user's answers. Once provided, analyze the input content based on their chosen summary type.

### Step 3: Propose Structure (Preview Phase)
**CRITICAL:** Do NOT generate the actual markdown file contents yet!
Present to the user a preview of the files to be created. For each proposed file, show:
- The suggested file path/name.
- The structure of the topics/headers (H1, H2, H3) that will be in that file.

Ask the user: "Do you approve this structure and the suggested file names, or would you like to make any changes before I generate the actual content?"

### Step 4: Final Generation
Wait for the user's approval.
If the user requests changes, go back to Step 3 and propose the updated structure.
Once the user explicitly approves the structure, generate the final markdown files in the agreed-upon directory and format. Use the necessary tool to save them.

## Important Constraints
- Be conversational but structured in the interview phase.
- Always enforce the preview step before doing large file generations.
