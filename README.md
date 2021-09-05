# ead_php_alura_mocks

> Projeto referente a [este](https://cursos.alura.com.br/course/php-mocks) curso.

## Doubles (dublês)

Diretamente do curso:

>  Objetos chamados de **Dummy** são objetos que, na verdade, nunca são utilizados. Normalmente servem apenas para preencher os requisitos dos parâmetros de algum método.

> Já os **Fakes** são implementações que realmente funcionam, mas normalmente tomam algum tipo de atalho que não os permitem ser utilizados em produção (um banco de dados em memória, por exemplo).

> Os **Stubs** fornecem respostas pré-definidas às chamadas dos métodos pré-definidos durante o teste. Normalmente não respondem ao que não forem explicitamente programados para responder.

> Enquanto isso, **Spies** são stubs, que também gravam algum tipo de informação, baseado em como foram utilizados. Um bom exemplo é um serviço de e-mail, que guarda quantas mensagens foram enviadas.

> Já os **Mocks** são os que estamos utilizando. São objetos pré-programados, com expectativas das mensagens (métodos e seus parâmetros) que vão receber.

## Disclaimer

Fiz a aula com o braço quebrado, portanto foi estudo mais passivo com copy/paste de código.

No vim possuo a função:

```vim
function! NN_GitAula2()
    let log = system("git log --pretty=format:\%s")
    vnew
    put=log
    normal! gg
    if search('^:zap: add aula')>0
        normal! 3W
        let s:numero_aula = expand('<cword>')+1
        echom system("git add -A && git commit -m \":zap: add aula ".s:numero_aula."\"")
    else
        echom system("git add -A && git commit -m \":zap: add aula 1\"")
    endif
    bdelete!
endfunction
```

E no terminal executava a cada zip novo de cada aula:

```sh
vim README.md -c "call NN_GitAula2()" -c qa!
```

## Setup inicial

```sh
composer i
```
