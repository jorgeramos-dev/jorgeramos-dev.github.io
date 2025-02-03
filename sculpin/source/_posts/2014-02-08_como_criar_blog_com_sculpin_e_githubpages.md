---
title: "Como criar um blog com Sculpin e hospedar no GiHub Pages"
date: 2014-02-08
---
Este repositório contém um blog estático gerado com [Sculpin](https://sculpin.io/) e hospedado no [GitHub Pages](https://pages.github.com/). Abaixo estão os passos para configurar e publicar o blog.

## Pré-requisitos

- [PHP](https://www.php.net/downloads.php)
- [Composer](https://getcomposer.org/download/)
- [Git](https://git-scm.com/)

## Passo 1: Instalar o Sculpin

1. Instale o Sculpin globalmente usando o Composer:

   ```bash
   composer global require sculpin/sculpin
   ```
Certifique-se de que o diretório ~/.composer/vendor/bin está no seu PATH.

## Passo 2: Criar um Novo Projeto Sculpin
Crie um novo projeto Sculpin:

```bash
sculpin init blog
```
Navegue até o diretório do projeto:

```bash
cd blog
```
Instale as dependências:
```bash
composer install
```

## Passo 3: Desenvolver o Blog
Adicione novas postagens na pasta source/_posts/. Por exemplo, crie um arquivo minha-primeira-postagem.md:

```bash
---
title: "Minha Primeira Postagem"
date: 2023-10-01
---
# Minha Primeira Postagem

Bem-vindo ao meu blog!

```

Gere o site para produção:

```bash
sculpin generate --env=prod
```

Os arquivos estáticos serão gerados na pasta output_prod/.

## Passo 4: Configurar o GitHub Pages
Crie um novo repositório no GitHub.

Inicialize o Git no seu projeto:

```bash
git init
git add .
git commit -m "Initial commit"
```

Adicione o repositório remoto:

```bash
git remote add origin https://github.com/seu-usuario/seu-repositorio.git
```

Envie o código para o GitHub:

```bash
git push -u origin master
```

Configure o GitHub Pages:

Vá para as configurações do repositório no GitHub.

Role até a seção "GitHub Pages".

Escolha a branch master (ou main) e a pasta / (root).

Salve as configurações.

## Passo 5: Publicar o Blog
Gere o site para produção:

```bash
sculpin generate --env=prod
```
Envie as alterações para o GitHub:

```bash
git add .
git commit -m "Atualizando o blog"
git push origin master
```

Acesse o blog em https://seu-usuario.github.io/seu-repositorio.

## Passo 6: Automatizar o Processo (Opcional)
Para automatizar o processo de geração e publicação, você pode criar um script ou usar uma ação do GitHub para gerar o site sempre que você fizer um push para o repositório.

## Conclusão
Agora você tem um blog estático gerado com Sculpin e hospedado no GitHub Pages. Personalize o tema, adicione mais postagens e continue a desenvolver seu blog conforme necessário.