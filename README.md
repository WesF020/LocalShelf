# Biblioteca Pessoal de eBooks em PDF

[![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)]()
[![Plataforma](https://img.shields.io/badge/plataforma-Linux-informational)]()
[![Python](https://img.shields.io/badge/python-3.11%2B-blue)]()
[![Licença](https://img.shields.io/badge/licen%C3%A7a-uso%20pessoal-lightgrey)]()

Aplicativo desktop **local e pessoal** para organizar eBooks em PDF como uma
biblioteca visual: capas, estantes, tags e retomada automática de leitura.

> **Sem nuvem. Sem login. Sem custo. Seus PDFs ficam no seu disco.**

---

## Descrição

O projeto resolve um problema recorrente de quem baixa eBooks em PDF: a
acumulação de arquivos com nomes confusos (`livro_final_v2.pdf`,
`978-85-...pdf`), sem identificação visual, sem organização e sem controle
de progresso de leitura.

O aplicativo oferece uma interface de biblioteca, com capas extraídas
automaticamente dos PDFs, metadados preenchidos via Open Library API e
retomada automática da página em que a leitura foi interrompida.

---

## Funcionalidades

| Recurso | Descrição |
|---|---|
| Biblioteca visual | PDFs exibidos como capas, não como arquivos |
| Capa automática | Extração da 1ª página do PDF (ou upload manual) |
| Busca e tags | Localização rápida de livros por título, autor ou tag |
| Retomada de leitura | Abertura automática na última página lida |
| Armazenamento local | Nenhum dado sai do computador do usuário |

---

## Público-alvo

Usuários que mantêm uma coleção pessoal de eBooks em PDF e desejam uma
ferramenta **simples** de organização, sem a complexidade de softwares
como Calibre, Obsidian ou Notion.

O projeto **não substitui** o Calibre e não é voltado para power users.
O foco é a leitura, não o gerenciamento avançado.

---

## Escopo negativo

Os itens abaixo estão **fora do escopo** desta versão:

- Sincronização com nuvem
- Sistema de login ou conta de usuário
- Conversão entre formatos (PDF ↔ EPUB)
- Anotações, highlights e marca-texto
- Distribuição de eBooks (o app apenas organiza arquivos do próprio usuário)

---

## Requisitos

- Linux (alvo principal: CachyOS / distribuições Arch-based)
- Python 3.11 ou superior
- PySide6 (instalado via `pip`)

> Suporte a Windows e macOS é tecnicamente possível, mas não testado
> nesta fase do desenvolvimento.

---

## Instalação

```bash
# 1. Clonar o repositório
git clone <url-do-repo>
cd biblioteca-pessoal

# 2. Criar ambiente virtual
python -m venv .venv
source .venv/bin/activate

# 3. Instalar dependências
pip install -r requirements.txt

# 4. Executar
python src/main.py
