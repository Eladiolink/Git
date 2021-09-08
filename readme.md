_Esse repositório está em construção e portanto pode ser modificado a ordem ou estrutura de como será passado as informções, e ainda será feita correções ortográficas pois os erros estão claros por enquanto rsrs_ 😅

_É importante também orientar que esse repositório tem como base apenas mostrar uma breve noção básica sobre os comando do git, e não explicar eles de fato. É fortemente indicado a leitura da [Documentação oficial do GIT](https://git-scm.com/docs/git/pt_BR)_

_Tendo essas considerações em mente... Tire bom proveito do conteúdo preparado!_ 😄
<br>

## Iniciando Trabalhos com o git...

Com esses comando vocês informará ao git quem você é com o seu nome e o seu email de usuario git :

  git config --local user.name "Teu nome sô"
  git config --local user.email "Teu email sô"

Para finalmente iniciar um repositorio git local, você terá que dá o comando:
  git init

Com esse comando será possível cirar um repositorio que guardará as alterações git, porém ele não armazeraná código, seria como um "sevidor" git:

  git init --bare

Para adicionar um arquivo ao monitoramento git basta dá:
  git add <arquivo a ser monitorado>

Para verificar o status das modificações feitas nos arquivos monitorados, basta o:

  git status

Para remover um arquivo do monirtoramento e remover um arquivo, basta o comando:

  git rm <arquivo>

Para salvar as mudanças feitos no código, temos o commando:
  git commit -m "Messagem para o commit"

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
   git remote add <nome do endereço> <pasta ou url>

Para verificar usa o comando:

   git remote -v

   Em que o  caminha _fetch_ será de onde o código será buscado e o _push_ é o caminho para onde o código será mandado.

Para clonar um repositorio basta apenas:

  git clone <endereço do repositorio>

Para sincronizar e atualizar nosso projeto local com o remoto basta o camando:

  git pull

Para enviar as mudanças feitas localmente para o repositorio remoto, usaremos o comanda:
  git push <nome do repositorio remoto> <banch que deseja enviar>


Para trabalhar com branchs basta usar o comando:

    *git branch - informas as branchs atuais
    *git branch <nome da branch> - cria uma nova branch

Para mudar de branch:
    *git checkout <nome da branch>
    *git checkout -b <nome  da branch> - cria e muda para a nova branch criada

Para unir branchs:
    *git merge <nome da branch> - fazerá a união da branch informada com a branch atual na qual está
    *git rebase <nome da branch> - Não cria um commit de merge

Para voltar um arquivo ao estado anterior:
    *git checkout -- <nome arquivo> - antes de commitar

Para reverter um commit feito usamos:
    *git revert <hash do commit atual a ser revertido>

Ou seja para reveter mudanças segue a ordem:
    *git checkout - antes de adicionalas
    *git reset - antes de commitar
    *git revert - após commitar

Para salvar as mudanças feitas temporariamente usamos o:
    *git stash - salva a mudança
    *git stash list - mostra a lista de salvamentos
    *git stash apply <numero na list> - aplica a mudança feita
    *git stash drop - apaga a mudança salva
    *git stash pop - aplica a última alteração salva, e apaga

Viagem no tempo usando o comando:
  *git checkout <hash do commit>

Mostra as mudanças feitas não salvas:
  *git diff

Mostra as mudanças feitas em um determinado commit:
  *git diff <hash do commit>

Adiciona uma tag atual:
  *git tag -a v0.1.0 -m "Menssagem na adição da tag"

Envia para o repositorio remoto a tag:
  *git push <repositorio remoto> <tag a ser enviada>
