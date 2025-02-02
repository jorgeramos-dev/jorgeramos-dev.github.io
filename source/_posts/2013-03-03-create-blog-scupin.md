---
title: Como Criar um Blog Rápido com Sculpin e Hospedar no GitHub Pages 
categories:
    - blog
tags:
    - sculpin
    - github

---
[Sculpin](https://sculpin.io/) é um gerador de sites estáticos em PHP que permite criar blogs e sites de forma rápida e eficiente. Combinado com o [GitHub Pages](https://pages.github.com/), você pode hospedar seu blog de graça. Vamos lá!

## Passo 1: Instalar o Sculpin

Primeiro, você precisa ter o PHP e o Composer instalados na sua máquina. Se ainda não os tem, siga as instruções no site oficial:

- [PHP](https://www.php.net/downloads.php)
- [Composer](https://getcomposer.org/download/)

Depois, instale o Sculpin globalmente via Composer:
```sh
composer global require sculpin/sculpin
```

## Passo 2: Criar um Novo Projeto Sculpin

Agora, crie um novo projeto Sculpin:

```sh
sculpin generate:blog meu-blog
cd meu-blog
```

Isso criará uma estrutura básica de blog na pasta meu-blog.

## Passo 3: Personalizar o Blog
Edite os arquivos na pasta source para personalizar o conteúdo do seu blog. Você pode modificar os arquivos Markdown (.md) para criar novas postagens ou ajustar o layout.

Por exemplo, para criar uma nova postagem, adicione um arquivo Markdown na pasta source/_posts:

```sh
markdown
---
title: "Minha Primeira Postagem"
date: 2023-10-01
---

# Bem-vindo ao meu blog!

Este é o conteúdo da minha primeira postagem.
```

## Passo 4: Gerar o Site Estático
Para gerar o site estático, execute o seguinte comando:

sculpin generate --env=prod
Isso criará os arquivos estáticos na pasta output_prod.

## Passo 5: Configurar o GitHub Pages
Crie um novo repositório no GitHub com o nome seu-usuario.github.io (substitua seu-usuario pelo seu nome de usuário no GitHub).

Inicialize um repositório Git no seu projeto Sculpin:
```sh
git init
git add .
git commit -m "Primeiro commit"
```
Adicione o repositório remoto do GitHub:
```sh
git remote add origin https://github.com/seu-usuario/seu-usuario.github.io.git
```
Envie o código para o GitHub:
```sh
git push -u origin master
```
Habilite o GitHub Pages no repositório:

Vá para as configurações do repositório no GitHub.

Role até a seção "Pages".

Selecione a branch master (ou main) e a pasta /(root).

Salve as alterações.

## Passo 6: Acessar o Blog
Depois de alguns minutos, seu blog estará disponível em:
```sh
https://seu-usuario.github.io
```

## Passo 7: Atualizar o Blog
Sempre que fizer alterações no blog, gere os arquivos estáticos novamente e envie as atualizações para o GitHub:
```sh
sculpin generate --env=prod
git add .
git commit -m "Atualização do blog"
git push origin master
```
## Conclusão
Pronto! Agora você tem um blog estático gerado com Sculpin e hospedado gratuitamente no GitHub Pages. Personalize-o conforme necessário e comece a compartilhar seu conteúdo com o mundo!
