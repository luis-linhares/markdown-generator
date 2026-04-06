# Markdown Generator Skill

A powerful and structured skill designed to seamlessly convert texts, URLs, files, and images into clean, formatted Markdown (`.md`) files. 

## What it does

This skill intercepts any user request to generate or format content into Markdown and enforces a reliable interactive workflow. Instead of generating long content right away, it guides the process to ensure the output matches exactly what you want.

### Key Features:
- **Multiple Output Formats:** Choose between:
  0. **Cópia Idêntica:** Exact same content, formatted strictly to Markdown.
  1. **Resumo Executivo (Executive Summary):** High-level concepts.
  2. **Pontos-Chave (Bullet Points):** Direct list of crucial numbers, facts, or takeaways.
  3. **Itens de Ação (Action Items):** What needs to be done.
  4. **Síntese Temática:** Topics grouped by main themes.
  5. **Personalizado:** Inform exactly what you want to extract.
- **Multi-File Support:** Break down large concepts into multiple files or keep everything in one document.
- **Safety Preview:** It generates a mock-up of the file structure and header organization *before* spending tokens/time on the final content generation. 

## How to Install

If you are using Anthropic's Claude Code or an agent environment that connects to `skills.sh`, you can just download or clone this repository into your local `.agents/skills/` directory.

```bash
git clone https://github.com/luis-linhares/markdown-generator.git .agents/skills/markdown-generator/
```

## How to Trigger

The skill's triggering mechanism has been optimized to be extremely smart. Try prompting your agent with phrases like:
- *"Pode converter a ata dessa reunião para markdown na opção de itens de ação?"*
- *"Gera um md a partir destas três imagens de figma que subi."*
- *"Exporta o README disso usando o texto que a gente conversou, dividido em 2 arquivos."*
- *"Toma esse texto aqui e me devolve no formato Markdown padrão de Resumo Executivo."*

---
*Created using the Skill Creator workflow.*
