# Guia de Boas Práticas para Trabalho em Equipe no GitHub

## Sobre o projeto

Este projeto foi desenvolvido pelo Grupo 3 com o objetivo de apresentar, de forma simples e didática, boas práticas para colaboração em equipe utilizando Git e GitHub.

## Integrantes

NAME/GitHub User

- André Chagas  — [ded3v]

- Milton Magalhães — [miltonmaglhaesv]

- Lucas Madureiro — [LucasMadureiro]

- Sergiofeitosaa — [Sergiofeitosaa]

## Sumário

1. [O que é um repositório](#1-o-que-é-um-repositório)
2. [O que são Issues](#2-o-que-são-issues)
3. [O que são Branches](#3-o-que-são-branches)
4. [Convenções de nomenclatura de branches](#4-convenções-de-nomenclatura-de-branches)
5. [O que são Pull Requests](#5-o-que-são-pull-requests)
6. [O que é Code Review](#6-o-que-é-code-review)
7. [Boas práticas para commits](#7-boas-práticas-para-commits)
8. [Como evitar conflitos](#8-como-evitar-conflitos)
9. [Exemplo prático de fluxo de trabalho](#9-exemplo-prático-de-fluxo-de-trabalho)
10. [Conclusão](#10-conclusão)

---

## 1. O que é um repositório

Um repositório (ou repo) é o espaço onde todo o código, histórico de alterações, arquivos e configurações de um projeto ficam armazenados. Pense nele como uma pasta inteligente que registra cada mudança feita ao longo do tempo.

O que um repositório contém?

Código-fonte — todos os arquivos do projeto (HTML, CSS, JS, Python etc.)
Histórico de commits — registro de cada alteração, com autor, data e mensagem
Branches e tags — linhas paralelas de desenvolvimento e marcações de versões
Documentação — README, licença e regras de contribuição

Tipos de repositório

Público — qualquer pessoa pode ver o código. Ideal para projetos open source.
Privado — apenas membros convidados têm acesso. Para projetos internos ou comerciais.

## 2. O que são Issues

Issues são registros de tarefas, bugs, sugestões ou discussões relacionadas ao projeto. Funcionam como um quadro de comunicação integrado ao repositório, onde a equipe acompanha o que precisa ser feito.

Tipos comuns de Issues

bug — relatar um comportamento incorreto ou erro no sistema
feature — solicitar ou propor uma nova funcionalidade
enhancement — sugerir melhoria em algo que já existe
docs — atualização ou criação de documentação
question — tirar dúvidas sobre o projeto
Boas práticas ao abrir uma Issue

Título claro e específico

❌ "Bug no app"
✅ "Erro 500 ao salvar perfil de usuário sem foto"

Descrição detalhada — explique o que aconteceu, o que era esperado e como reproduzir o problema.
Use labels e atribua responsáveis — isso facilita a triagem e garante que cada issue tenha um dono.
Vincule ao Pull Request — use Closes #42 na descrição do PR para fechar a issue automaticamente após o merge.

## 3. O que são Branches

Uma branch (ramo) é uma linha paralela de desenvolvimento dentro do repositório. Ela permite trabalhar em novas funcionalidades, correções ou experimentos sem afetar o código principal.

A branch principal normalmente recebe o nome de:

main
Exemplo Prático

Imagine que a equipe deseja criar uma funcionalidade de login.

Em vez de alterar diretamente a branch principal, cria-se uma nova branch:

git checkout -b feature/login

Fluxo de trabalho:

main
 │
 └── feature/login
      ├── Criar tela de login
      ├── Implementar autenticação
      └── Realizar testes

Após a conclusão, as alterações são incorporadas à branch principal por meio de um Pull Request.

Fluxo básico de uma branch

bash
#1. Criar a branch
git checkout -b feature/cadastro-usuario

#2. Fazer commits normalmente
git add .
git commit -m "feat: adiciona formulário de cadastro"

#3. Enviar para o repositório remoto
git push origin feature/cadastro-usuario

#4. Abrir um Pull Request no GitHub para revisão

## 4. Convenções de nomenclatura de branches

O padrão mais utilizado é tipo/descricao-curta. Isso facilita a comunicação, organização e automação de pipelines.

Prefixos mais utilizados:
feature/ — nova funcionalidade → feature/autenticacao-oauth
fix/ ou bugfix/ — correção de bug não-urgente → fix/erro-ao-salvar-formulario
hotfix/ — correção crítica direto para produção → hotfix/falha-no-checkout
refactor/ — melhoria de código sem mudar comportamento → refactor/servico-de-pagamento
docs/ — atualização de documentação → docs/atualizar-readme
test/ — adição ou melhoria de testes → test/cobertura-modulo-auth
chore/ — tarefas de manutenção (CI, dependências) → chore/atualizar-dependencias

Regras de ouro:
✅ Use letras minúsculas e hífens para separar palavras
✅ Seja descritivo, mas conciso
✅ Inclua o número da Issue quando houver: feature/42-login-social
❌ Evite nomes genéricos como minha-branch, teste ou fix2
❌ Não use espaços, underscores ou letras maiúsculas

## 5. O que são Pull Requests

Pull Request (PR) é a forma de propor a integração de uma branch ao código principal. É o momento de revisão colaborativa — o time analisa as mudanças antes do merge.

Fluxo resumido:
branch feature → Pull Request → revisão do time → merge na main

Boas práticas:
Descreva o que foi feito e por quê
Referencie a Issue relacionada com Closes #número
Mantenha o PR pequeno e focado em um único objetivo
Solicite revisão de pelo menos um colega antes de fazer o merge

Exemplo Prático
Criar uma branch:
git checkout -b feature/login
Realizar as alterações e enviar para o GitHub:
git add .
git commit -m "Adiciona funcionalidade de login"
git push origin feature/login
Abrir um Pull Request no GitHub:
feature/login → main
Após a aprovação, realizar o merge da branch.

## 6. O que é Code Review

O Code Review é o processo de revisão das alterações realizadas por outro desenvolvedor antes que elas sejam incorporadas ao projeto.

O objetivo não é apenas encontrar erros, mas também melhorar a qualidade do código, compartilhar conhecimento entre a equipe e garantir que as boas práticas estejam sendo seguidas.

Durante um Code Review é comum verificar:

* Se o código está funcionando corretamente.
* Se a solução atende ao objetivo da tarefa.
* Se existem oportunidades de simplificação.
* Se a documentação foi atualizada quando necessário.
* Se as convenções do projeto foram respeitadas.

Um bom Code Review ajuda a reduzir bugs, aumenta a qualidade do software e promove o aprendizado entre os integrantes da equipe.

## 7. Boas práticas para commits e exemplos

Um commit representa um registro das alterações realizadas no projeto. Para facilitar o entendimento do histórico, recomenda-se que cada commit seja pequeno, objetivo e tenha uma mensagem clara.


**Boas práticas**

* Fazer commits frequentes.
* Escrever mensagens curtas e descritivas.
* Alterar apenas um assunto por commit.
* Evitar mensagens genéricas como “alterações” ou “teste”.
* Utilizar prefixos para indicar o tipo da alteração.


**Prefixos mais utilizados:**

feat:            Nova funcionalidade

fix:             Correção de erro

docs:            Alteração na documentação

style:           Ajustes de formatação

refactor:        Refatoração sem alterar comportamento

test:            Inclusão ou alteração de testes

chore:           Tarefas de manutenção do projeto


**Exemplos de mensagens de commit:**

docs: adiciona seção sobre Pull Requests

feat: implementa tela de login

fix: corrige erro de autenticação

style: ajusta formatação do README

refactor: simplifica validação de usuários

## 8. Como evitar conflitos

Em um trabalho em equipe, conflitos podem acontecer quando duas ou mais pessoas alteram a mesma parte de um arquivo ao mesmo tempo. No Git, isso costuma acontecer principalmente quando vários integrantes editam as mesmas linhas de um mesmo arquivo, como o `README.md`.

Para evitar conflitos, a equipe deve seguir algumas boas práticas:

* Cada integrante deve trabalhar em uma branch própria;
* Cada pessoa deve editar somente a seção pela qual ficou responsável;
* Antes de começar uma nova alteração, é importante atualizar a branch `main`;
* Antes de finalizar um Pull Request, a branch de trabalho deve estar atualizada com a versão mais recente da `main`;
* O grupo deve combinar previamente quem será responsável por cada parte do README;
* Mudanças em seções de outra pessoa devem ser avisadas antes no grupo.

Exemplo de atualização da branch `main` antes de começar:

```bash
git checkout main
git pull origin main
```

Depois disso, o integrante pode criar sua branch de trabalho:

```bash
git checkout -b docs/conflitos-fluxo-pratico
```

Essa prática reduz bastante o risco de conflitos, porque cada pessoa trabalha em uma parte separada do projeto.


## 9. Exemplo prático de fluxo de trabalho

Para entender melhor como funciona o trabalho em equipe no GitHub, imagine a seguinte situação: um integrante ficou responsável por escrever a seção sobre conflitos e fluxo prático do README.

Primeiro, ele clona o repositório do grupo:

```bash
git clone https://github.com/USUARIO/guia-boas-praticas-github-grupo-3.git
```

Depois entra na pasta do projeto:

```bash
cd guia-boas-praticas-github-grupo-3
```

Em seguida, cria uma branch própria para a sua tarefa:

```bash
git checkout -b docs/conflitos-fluxo-pratico
```

Depois, abre o projeto em sua IDE ou editor de código e edita somente a parte do README relacionada à sua Issue.

Após finalizar a edição, verifica quais arquivos foram modificados:

```bash
git status
```

Em seguida, adiciona o arquivo alterado:

```bash
git add README.md
```

Depois cria um commit com uma mensagem clara:

```bash
git commit -m "docs: adiciona seção sobre conflitos e fluxo prático"
```

Após o commit, envia a branch para o GitHub:

```bash
git push -u origin docs/conflitos-fluxo-pratico
```

Depois disso, o integrante acessa o repositório no GitHub e abre um Pull Request da sua branch para a branch `main`.

Na descrição do Pull Request, ele pode relacionar a Issue correspondente usando:

```text
Closes #NUMERO-DA-ISSUE
```

Exemplo:

```text
Closes #4
```

Após a abertura do Pull Request, outro integrante do grupo deve revisar o conteúdo.
Se estiver tudo correto, o Pull Request pode ser aprovado e incorporado à branch `main`.

Esse fluxo representa uma prática real de colaboração no GitHub, utilizando Issue, Branch, Commit, Pull Request e Code Review.
.

## 10. Conclusão

O uso correto do Git e do GitHub ajuda uma equipe a trabalhar de forma mais organizada, segura e colaborativa. Ao dividir as tarefas por Issues, criar branches próprias, fazer commits claros e abrir Pull Requests, o grupo consegue acompanhar melhor o andamento do projeto e reduzir erros durante o desenvolvimento.

Também é importante evitar alterações diretamente na branch `main`, manter a comunicação entre os integrantes e atualizar a branch de trabalho antes de finalizar um Pull Request. Essas práticas diminuem a chance de conflitos e facilitam a revisão do código ou da documentação.

Portanto, seguir um fluxo de trabalho bem definido torna o projeto mais profissional e aproxima a equipe de práticas utilizadas em ambientes reais de desenvolvimento de software.

---

## Tecnologias utilizadas

- Git
- GitHub
- Markdown
- Visual Studio Code

## Licença

Projeto desenvolvido para fins educacionais.
