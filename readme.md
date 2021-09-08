_Esse repositório está em construção e portanto pode ser modificado a ordem ou a estrutura de como será passado as informções, e ainda será feita correções ortográficas_ 😅

_É importante também orientar que esse repositório tem como base apenas dá passar uma breve informação sobre os comando basicos do git e não explicar eles de fato, é fortemente indicado a leitura da [Documentação oficial do GIT](https://git-scm.com/docs/git/pt_BR)_

_Tendo essas considerações em mente... Tire bom proveito do conteúdo preparado!_ 😄
<br>

## Iniciando Trabalhos com o git...

Com esses comando vocês informará ao git quem você é com o seu nome e o seu email de usuario git :

*  git config --local user.name "Teu nome sô"
*  git config --local user.email "Teu email sô"

Para finalmente iniciar um repositorio git local, você terá que dá o comando:
*  git init

Com esse comando será possível cirar um repositorio que guardará as alterações git, porém ele não armazeraná código, seria como um "sevidor" git:

*  git init --bare

Para adicionar um arquivo ao monitoramento git basta dá:
*  git add [_arquivo a ser monitorado_]

Para verificar o status das modificações feitas nos arquivos monitorados, basta o:

*  git status

Para remover um arquivo do monirtoramento e remover um arquivo, basta o comando:

*  git rm [_Arquivo_]

Para salvar as mudanças feitos no código, temos o commando:
*  git commit -m "Messagem para o commit"

  Note que o _-m_ é para informar a mensagem do commit, caso não seja informado
  o git abrirá uma editor de texto para você esprecre uma mensagem mais longa,
  em que a 1º Linha é o titulo do commit, e o restante é o texto descritivo respectivamente.

Definições usadas pelo o Git:

* *HEAD*: Estado atual do nosso código, ou seja, onde o Git os colocou

* *Working tree*: Local onde os arquivos realmente estão sendo armazenados e editados

* *index*: Local onde o Git armazena o que será commitado, ou seja, o local entre a working tree e o repositório Git em si.

Para verificar o historico de modificações podemos usar o comando:

* git log

Outra forma de verificar o log de commits:

Mostra historico em apenas uma linha por commit:

* git log --oneline
* git log -p
* git log --graph

No site [devhints](https://devhints.io/git-log) tem uma boa explicação sobre

Adicionar um endereço remoto do git:
*   git remote add [_Nome do endereço_] [_Pasta ou url_]

Para verificar usa o comando:

*   git remote -v

   Em que o  caminha _fetch_ será de onde o código será buscado e o _push_ é o caminho para onde o código será mandado.

Para clonar um repositorio basta apenas:

*  git clone [_Endereço do repositorio_]

Para sincronizar e atualizar nosso projeto local com o remoto basta o camando:

*  git pull

Para enviar as mudanças feitas localmente para o repositorio remoto, usaremos o comanda:
*  git push [_Nome do repositorio remoto_] [_Banch que deseja enviar_]


Para trabalhar com branchs basta usar o comando:

*  git branch - informas as branchs atuais
*  git branch <nome da branch> - cria uma nova branch

Para mudar de branch:
*  git checkout <nome da branch>
*  git checkout -b [_Nome da branch_] - cria e muda para a nova branch criada

Para unir branchs:
*  git merge [_Nome da branch_] - fazerá a união da branch informada com a branch atual na qual está

*  git rebase [_Nome da branch_] - Não cria um commit de merge

Para voltar um arquivo ao estado anterior:
*  git checkout -- [_Nome arquivo_] - antes de commitar

Para reverter um commit feito usamos:
*  git revert [_Hsh do commit atual a ser revertido_]

Ou seja para reveter mudanças segue a ordem:
*  git checkout - antes de adicionalas
*  git reset - antes de commitar
*  git revert - após commitar

Para salvar as mudanças feitas temporariamente usamos o:
*  git stash - salva a mudança
*  git stash list - mostra a lista de salvamentos
*  git stash apply [_Numero na lista_] - aplica a mudança feita
*  git stash drop - apaga a mudança salva
*  git stash pop - aplica a última alteração salva, e apaga

Viagem no tempo usando o comando:
*  git checkout [_Hash do commit_]

Mostra as mudanças feitas não salvas:
*  git diff

Mostra as mudanças feitas em um determinado commit:
*  git diff [_Hash do commit_]

Adiciona uma tag atual:
*  git tag -a v0.1.0 -m "Menssagem na adição da tag"

Envia para o repositorio remoto a tag:
*  git push [_Repositorio remoto_] [_Tag a ser enviada_]

## Ao Infinito..... E além!

Unindo vários commits em um só:

* git rebase -i HEAD~[_Número de commits_]
 <br/>
Exemplo:
     git commit -i HEAD~3
ou
* git rebase -i [_Hash do commit anterior ao qual o começa a união_]
<br>
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