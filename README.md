# Exercício — Documentar os comandos do Git

---

## O que é este repositório

Este repositório contém **11 arquivos Markdown**, um para cada seção do
[GitHub Git Cheat Sheet (pt-BR)](https://training.github.com/downloads/pt_BR/github-git-cheat-sheet/).

Cada arquivo lista os comandos daquela seção.
Cada comando vem com o campo de explicação **em branco**.

Ao todo são **37 itens** a preencher e fazer os merges

---

## O que você tem que fazer

Preencher, com as suas palavras, a explicação de cada comando.

Cada item tem dois campos:

| Campo | Obrigatório? | O que escrever |
| --- | --- | --- |
| **O que faz** | sim | o efeito do comando, em uma ou duas frases |
| **Quando usar / observação** | não | uma situação real, uma pegadinha, uma variação útil |

Os campos estão marcados com `<!-- TODO -->`.
Apague o comentário `TODO` e escreva no lugar dele.

Para achar o que ainda falta: Abrir cada arquivo no navegador (via GitHub) ou na IDE (VSCode ou outro)

### Regras

1. **Explique com as suas palavras.**
   Evite copiar a descrição do cheat sheet ou colar a saída de um assistente de IA.
   Essa explicação deveria mostrar que você entendeu o efeito do comando.

2. **Uma frase por linha.**
   O Git compara arquivos linha a linha.
   Parágrafo escrito em uma única linha vira um conflito enorme e ilegível quando duas pessoas editam o mesmo trecho.
   Escrevendo uma frase por linha, o merge automático resolve quase tudo sozinho.

3. **Um commit por arquivo concluído.**
   Nada de `git add .` no fim, com tudo de uma vez.
   O histórico tem que mostrar o seu percurso.

4. **Mensagens no padrão [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/).**

   ```text
   docs(faca-mudancas): explica os seis comandos da secao
   docs(salve-fragmentos): explica git stash e git stash pop
   fix(revise-o-historico): corrige a explicacao de git show
   ```

5. **Marque o checklist.**
   Cada arquivo termina com uma lista de tarefas.
   Troque `- [ ]` por `- [x]` conforme for preenchendo — o GitHub renderiza como caixas marcadas.

6. **Não altere o comando em si.**
   O bloco de código de cada item é a referência oficial.
   Se achar que há um erro nele, escreva isso no campo de observação, mas não edite o bloco.

---

## Branches e arquivos

Cada seção do cheat sheet vive em **um arquivo** e é trabalhada em **uma branch própria**.
A `main` contém apenas este `README.md` e o índice — o conteúdo chega nela por merge.

| Branch | Arquivo | Seção | Itens | Do que trata |
| --- | --- | --- | --- | --- |
| `docs/01-instale-o-git` | [01-instale-o-git.md](01-instale-o-git.md) | Instale o Git | 3 | Onde obter o Git e os clientes desktop do GitHub |
| `docs/02-configure-a-ferramenta` | [02-configure-a-ferramenta.md](02-configure-a-ferramenta.md) | Configure a ferramenta | 2 | Identidade do autor: nome e e-mail gravados em cada commit |
| `docs/03-crie-repositorios` | [03-crie-repositorios.md](03-crie-repositorios.md) | Crie repositórios | 2 | As duas formas de começar: criar do zero (`init`) ou copiar um existente (`clone`) |
| `docs/04-faca-mudancas` | [04-faca-mudancas.md](04-faca-mudancas.md) | Faça mudanças | 6 | O ciclo do dia a dia: diretório de trabalho → área de preparação → commit |
| `docs/05-mudancas-em-grupo` | [05-mudancas-em-grupo.md](05-mudancas-em-grupo.md) | Mudanças em grupo | 5 | Branches: criar, trocar, integrar e apagar linhas de trabalho paralelas |
| `docs/06-refatore-nomes-de-arquivos` | [06-refatore-nomes-de-arquivos.md](06-refatore-nomes-de-arquivos.md) | Refatore nomes de arquivos | 3 | Remover e renomear arquivos **sob** controle de versão, não por fora dele |
| `docs/07-suprima-o-monitoramento` | [07-suprima-o-monitoramento.md](07-suprima-o-monitoramento.md) | Suprima o monitoramento | 2 | `.gitignore`: o que nunca deve entrar no repositório |
| `docs/08-salve-fragmentos` | [08-salve-fragmentos.md](08-salve-fragmentos.md) | Salve fragmentos | 4 | `stash`: guardar trabalho incompleto sem commitar |
| `docs/09-revise-o-historico` | [09-revise-o-historico.md](09-revise-o-historico.md) | Revise o histórico | 4 | Ler o passado do projeto: log, diferenças entre branches, conteúdo de um commit |
| `docs/10-desfaca-commits` | [10-desfaca-commits.md](10-desfaca-commits.md) | Desfaça commits | 2 | `reset`: voltar atrás, com e sem descartar o trabalho |
| `docs/11-sincronize-mudancas` | [11-sincronize-mudancas.md](11-sincronize-mudancas.md) | Sincronize mudanças | 4 | Conversar com o repositório remoto: fetch, push, pull |
| | | **Total** | **37** | |

Para ver todas as branches depois do clone:

```bash
git fetch --all
git branch -a
```

Uma branch tem uma finalidade só.
Não trabalhe o arquivo 04 estando na branch do arquivo 07 — o histórico deixa de contar a verdade sobre o que você fez.

---

## Fluxo sugerido

O trabalho tem duas fases, e a **ordem importa nas duas**:

1. **Preencher** as branches na ordem crescente — da `01` até a `11`.
2. **Integrar** na `main` na ordem inversa — da `11` até a `01`.

### 1. Faça o fork

Abra o repositório da disciplina no GitHub e clique em **Fork**.
Isso cria uma cópia independente na sua conta, com todas as branches.

### 2. Clone o **seu** fork

Copie a URL pelo botão verde **Code** do seu fork — não a do repositório original.

```bash
git clone https://github.com/<seu-usuario>/<nome-do-repositorio>.git
cd <nome-do-repositorio>

git remote -v      # as duas linhas devem conter o SEU usuário
git fetch --all
git branch -a      # confira que as 11 branches estão aqui
```

Se `git remote -v` mostrar o usuário do professor, você clonou o repositório errado.
Apague a pasta e refaça este passo.

### 3. Configure a ferramenta

```bash
git config user.name  "Seu Nome"
git config user.email "seu-email@algumacoisa.com.br"

# mostra também a versão BASE dentro do marcador de conflito (Git >= 2.35)
git config merge.conflictStyle zdiff3
```

A última linha vai fazer diferença na fase 2.
Sem ela você enxerga só "o meu" e "o dele", e resolve o conflito no chute.

---

## Fase 1 — Preencher, da branch 01 até a 11

Percorra as branches **na ordem crescente**.
Em cada uma você faz duas coisas: preenche o arquivo da seção **e** atualiza o índice do `README.md`.

```bash
# 1. entra na branch da seção
git switch docs/02-configure-a-ferramenta

# 2. preenche o arquivo daquela seção
$ABRE NO EDITOR comandos/02-configure-a-ferramenta.md
git add comandos/02-configure-a-ferramenta.md
git commit -m "docs(configure-a-ferramenta): explica os comandos de configuracao"

# 3. envia commits para origin (Repositório no GitHub)
git push

# 4. marca a linha correspondente no índice do README.md
$ABRE NO EDITOR README.md
git add README.md
git commit -m "docs(readme): marca a secao 02 como concluida"

# 5. envia commits para origin (Repositório no GitHub)
git push
```

Repita para as 11 branches, em ordem.
Cada branch termina com **dois commits**: um do arquivo da seção, um do índice.

Ao fim da fase 1:

```bash
git switch main
git log --graph --oneline --all --decorate
```

Você deve ver 11 branches saindo do mesmo ponto, todas paralelas, e a `main` ainda parada.
Nenhuma delas conhece o trabalho das outras — é isso que torna a fase 2 interessante.

> IMPORTANTE: Não faça merge nenhum durante a fase 1.
> A ideia é acumular as 11 linhas de trabalho e só depois integrá-las.

---

## Fase 2 — Integrar, iniciando da branch 11 até a 01

Agora o caminho de volta. Sempre a partir da `main`

```bash
git switch main
git merge nome-do-branch
git push
```

> IMPORTANTE: É uma boa prática primeiro atualizar o branch XYZ com a main antes de levar o branch XYZ para a main

> Confira no `README.md` da `main` e nos demais arquivos

---

## Índice

| # | Arquivo | Seção | Itens | Concluído |
| --- | --- | --- | --- | --- |
| 01 | [01-instale-o-git.md](comandos/01-instale-o-git.md) | Instale o Git | 3 | [X] |
| 02 | [02-configure-a-ferramenta.md](comandos/02-configure-a-ferramenta.md) | Configure a ferramenta | 2 | [ ] |
| 03 | [03-crie-repositorios.md](comandos/03-crie-repositorios.md) | Crie repositórios | 2 | [ ] |
| 04 | [04-faca-mudancas.md](comandos/04-faca-mudancas.md) | Faça mudanças | 6 | [ ] |
| 05 | [05-mudancas-em-grupo.md](comandos/05-mudancas-em-grupo.md) | Mudanças em grupo | 5 | [ ] |
| 06 | [06-refatore-nomes-de-arquivos.md](comandos/06-refatore-nomes-de-arquivos.md) | Refatore nomes de arquivos | 3 | [ ] |
| 07 | [07-suprima-o-monitoramento.md](comandos/07-suprima-o-monitoramento.md) | Suprima o monitoramento | 2 | [ ] |
| 08 | [08-salve-fragmentos.md](comandos/08-salve-fragmentos.md) | Salve fragmentos | 4 | [ ] |
| 09 | [09-revise-o-historico.md](comandos/09-revise-o-historico.md) | Revise o histórico | 4 | [ ] |
| 10 | [10-desfaca-commits.md](comandos/10-desfaca-commits.md) | Desfaça commits | 2 | [ ] |
| 11 | [11-sincronize-mudancas.md](comandos/11-sincronize-mudancas.md) | Sincronize mudanças | 4 | [ ] |
| | | **Total** | **37** | |

Marque a coluna **Concluído** com `[x]` conforme for fechando cada arquivo.

---

## Sobre a fonte

O conteúdo destes arquivos foi extraído do
[GitHub Git Cheat Sheet em português](https://training.github.com/downloads/pt_BR/github-git-cheat-sheet/),
publicado pelo GitHub sob o repositório [`github/training-kit`](https://github.com/github/training-kit).
