
---
# Roadmap

Documento de acompanhamento do desenvolvimento da Biblioteca Pessoal de
eBooks em PDF.

## Legenda de status

| Símbolo | Significado |
|---|---|
| `[x]` | Concluído |
| `[~]` | Em andamento |
| `[ ]` | Planejado |
| `[i]` | Ideia futura (fora do MVP) |

---

## Fase 0 — Setup

**Objetivo:** ter uma janela Qt abrindo no ambiente de desenvolvimento.

- [ ] Criar estrutura de pastas do projeto
- [ ] Configurar ambiente virtual Python
- [ ] Instalar PySide6 e dependências
- [ ] Executar "Hello World" em Qt (janela vazia)
- [ ] Validar execução no CachyOS com `QT_QPA_PLATFORM=xcb`

**Critério de conclusão:** janela vazia do Qt abrindo sem erros.

---

## Fase 1 — Banco de dados

**Objetivo:** inserir, listar e remover livros via terminal.

- [ ] Criar `db.py`
- [ ] Implementar schema SQLite (`books`, `tags`, `book_tags`)
- [ ] Implementar funções CRUD para livros
- [ ] Implementar funções CRUD para tags
- [ ] Escrever testes básicos em `tests/test_db.py`

**Critério de conclusão:** operações CRUD funcionando via script de teste.

---

## Fase 2 — Biblioteca visual

**Objetivo:** visualizar a biblioteca (mesmo sem capas reais) e buscar por título.

- [ ] `library_view.py` com `QListView` em modo ícone
- [ ] Leitura de livros do banco e exibição em grid
- [ ] Placeholder para livros sem capa
- [ ] Layout responsivo (redimensionamento com a janela)
- [ ] Barra de busca no topo com filtro em tempo real

**Critério de conclusão:** biblioteca renderizando e busca funcionando.

---

## Fase 3 — Adição de livros

**Objetivo:** adicionar um PDF real, com capa e metadados preenchidos.

- [ ] `book_dialog.py` com `QFileDialog`
- [ ] Inserção de registro no banco após seleção do PDF
- [ ] `metadata.py` — extração de capa da 1ª página com `QPdfDocument`
- [ ] Salvamento da capa em `data/covers/`
- [ ] Consulta à Open Library API (título, autor)
- [ ] Tela de confirmação com campos editáveis

**Critério de conclusão:** fluxo completo de adição de um PDF funcional.

---

## Fase 4 — Leitor

**Objetivo:** abrir um livro, ler, fechar e reabrir na mesma página.

- [ ] `reader_view.py` com `QPdfView`
- [ ] Carregamento do PDF selecionado
- [ ] Salvamento de `current_page` a cada troca de página
- [ ] Botão "Continuar lendo (pág. N)" na tela de detalhe
- [ ] Carregamento assíncrono em `QThreadPool` para PDFs grandes

**Critério de conclusão:** retomada de leitura funcionando de ponta a ponta.

---

## Fase 5 — Polimento

**Objetivo:** tornar o aplicativo agradável para uso diário.

- [ ] Sistema de tags (adicionar, remover, filtrar)
- [ ] Ordenação (título, autor, data de adição, último lido)
- [ ] Tema escuro e claro
- [ ] Atalhos de teclado (Ctrl+F, Ctrl+N, Esc)
- [ ] Menu de contexto (botão direito): editar, remover, abrir pasta
- [ ] Estilização com QSS

**Critério de conclusão:** aplicativo utilizável no dia a dia sem fricções.

---

## Fase 6 — Empacotamento

**Objetivo:** distribuir o aplicativo sem exigir instalação de Python.

- [ ] Configurar PyInstaller
- [ ] Gerar `.AppImage` para Linux
- [ ] Testar binário fora do ambiente de desenvolvimento
- [ ] Documentar instalação no `README.md`

**Critério de conclusão:** binário executável gerado e validado.

---

## Fase 7 — Testes e uso real

**Objetivo:** validar que o aplicativo resolve o problema original.

- [ ] Utilizar o aplicativo por 1–2 semanas com a biblioteca pessoal real
- [ ] Registrar dores e fricções de uso
- [ ] Corrigir bugs encontrados
- [ ] Ajustar experiência de uso com base no feedback

**Critério de conclusão:** aplicativo substituindo o fluxo anterior de leitura.

---

## Ideias futuras (fora do MVP)

- [i] Anotações e highlights no PDF
- [i] Marca-páginas
- [i] Estatísticas de leitura (tempo, páginas por dia)
- [i] Exportação de biblioteca para CSV ou JSON
- [i] Suporte a formato EPUB
- [i] Versão mobile (avaliação de Tauri ou Flutter)
- [i] Sincronização via pasta compartilhada (Syncthing, Drive)
- [i] Busca full-text dentro dos PDFs

---

## Princípios do projeto

1. **Local-first** — nenhum dado sai da máquina do usuário
2. **Custo zero** — sem servidor, sem nuvem, sem assinatura
3. **Simples antes de poderoso** — foco no usuário comum
4. **Desenvolvimento incremental** — um arquivo por vez, testado a cada passo

---

## Estimativa geral

**Prazo:** 3 a 5 semanas em ritmo part-time (1–3h por dia, 4–5 dias por semana).

**Método:** desenvolvimento assistido por LLM em plano gratuito, seguindo o
guia presente em [`PROJETO.md`](./PROJETO.md).
