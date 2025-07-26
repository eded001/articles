## Git e GitHub

“Git e GitHub são a mesma coisa?” Não. Nem de longe. E entender a diferença é essencial pra não passar vergonha.

* **Git** é uma ferramenta de controle de versão. Ela roda localmente no seu computador e registra tudo que você faz no seu código, como uma linha do tempo completa do seu projeto.

* **GitHub** é uma plataforma online onde você armazena repositórios Git. Permite colaboração entre devs, revisão de código, issues, automações, pull requests e mais.

![Git vs GitHub](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/o-que-git-e-uma-marca-de-gloss/imgs/git-vs-github.jpg)

**Resumo:**

* Git = ferramenta de versionamento (local)
* GitHub = plataforma online que hospeda repositórios Git

Você pode usar Git sem GitHub. Mas GitHub sem Git não existe.

```
[ Seu PC com Git ] ────────> [ GitHub ]
     (local)                    (online)
```

---

## Por que usar Controle de Versão

Versionamento de código é como uma máquina do tempo. Cada alteração vira um commit, com:

* O que foi alterado
* Quando foi alterado
* Quem alterou

Isso organiza o caos, permite testes sem medo e mantém tudo rastreável.

**Exemplo:**

```
[ Commit 1 ]
    "Projeto criado"

      │
      ▼
[ Commit 2 ]
    "Adiciona login"

      │
      ▼
[ Commit 3 ]
    "Corrige bug no login"
```

Você pode criar **branches** para testar funcionalidades isoladas sem afetar o código principal.

---

## Instalação do Git

### Baixe e instale

Acesse: [https://git-scm.com/downloads](https://git-scm.com/downloads)
Baixe de acordo com seu sistema operacional.

### Configure seu nome e e-mail

```bash
git config --global user.name "Fulano de Tal"
git config --global user.email fulano@exemplo.com
```

---

## Criando um Repositório do Zero

### Crie um repositório no GitHub

Acesse seu perfil e clique em **"New Repository"**.
Desative a opção **"Add a README.md"** para clonar com um repositório limpo.

### No terminal, rode os comandos:

```bash
git init
echo "# nome-do-repositorio" > README.md
git add README.md
git commit -m "primeiro commit"
git branch -M main
git remote add origin https://github.com/seu-usuario/repositorio.git
git push -u origin main
```

**Fluxo:**

```
[ git init ]
     │
[ git add README.md ]
     │
[ git commit -m "mensagem" ]
     │
[ git branch -M main ]
     │
[ git remote add origin <url> ]
     │
[ git push -u origin main ]
```

---

## Clonando um Repositório

Quer pegar um projeto já existente do GitHub?

```bash
git clone https://github.com/usuario/repositorio.git
```

**Fluxo:**

```
[ GitHub ] ────────> [ Seu PC ]
          (clone)
```

---

## Atualizando seu projeto com alterações remotas

Está colaborando com outros devs e quer pegar as últimas mudanças?

```bash
git pull
```

**Fluxo:**

```
[ GitHub ] ────────> [ Seu PC ]
          (pull)
```

---

## Enviando alterações pro repositório remoto

Depois de fazer alterações no código:

```bash
git add .
git commit -m "mensagem clara do que foi feito"
git push
```

**Fluxo:**

```
[ Seu PC ] ────────> [ GitHub ]
          (push)
```

---

## Dicas importantes

* Faça commits pequenos e frequentes
* Escreva mensagens claras no commit
* Use branches pra testar novas funcionalidades
* Sempre use `git pull` antes de `git push` pra evitar conflitos

---

## Referência

* [https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Sobre-Controle-de-Vers%C3%A3o](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Sobre-Controle-de-Vers%C3%A3o)