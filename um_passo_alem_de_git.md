# Ao Infinito..... E além!

Unindo vários commits em um só:

* git rebase -i HEAD~[_Número de commits_]
Exemplo:
     git commit -i HEAD~3
ou
* git rebase -i [_Hash do commit anterior ao qual o começa a união_]
Exemplo:
     git commit -i 3bf3re3
* pick - Deixar
* s - Juntar

Após pedirá para você informar uma nova mensagem ao commit

Para pegar as mudanças feitas em um commit especifico e trazer ele para uma determinada branch atual, basta fazer o Cherry-pick, com o comando:

* git cherry-pick [_Hash do commit_]

Ver uma alteração feita em um commit especifico:

* git bisect start -> Inicia a busca
* git bisect bad HEAD -> Commit Atual
* git bisect good [_Hash do commit_] -> Onde estava bom
* git bisect bad -> se não encontrou o problema
* git bisect good -> se encontrou o problema
* git bisect reset -> para finalizar a busca

Para mostrar tudo o que foi feito no commit, usa o comando:

* git show [_Hash do commit_]

Para encontrar quem fez a alteração em um certo arquivo:

* git blame [_arquivo desejado_]

#### Tópicos Indicados
Recomendo você dá uma pesquisada sobre os seguintes temas 😉:
* Gitflow
* Ferramentas Git visuais
* GitHooks