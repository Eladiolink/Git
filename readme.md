_Esse repositório está em construção e portanto pode ser modificado a ordem ou estrutura de como será passado as informções, e ainda será feita correções ortográficas pois os erros estão claros por enquanto rsrs_ 😅

_É importante também orientar que esse repositório tem como base apenas mostrar uma breve noção básica sobre os comando do git, e não explicar eles de fato. É fortemente indicado a leitura da [Documentação oficial do GIT](https://git-scm.com/docs/git/pt_BR)_

_Tendo essas considerações em mente... Tire bom proveito do conteúdo preparado!_ 😄
<br>

## Iniciando Trabalhos com o git...

Com esses comando vocês informará ao git quem você é com o seu nome e o seu email de usuario git :

```shell
git config --local user.name "Teu nome sô"
git config --local user.email "Teu email sô"
```

**Init**
Para finalmente iniciar um repositorio git local, você terá que dá o comando:

```shell
git init
```
Com esse comando será possível cirar um repositorio que guardará as alterações git, porém ele não armazeraná código, seria como um "sevidor" git:

```shell
git init --bare
```

**Add**
Para adicionar um arquivo ao monitoramento git basta dá:

```shell
git add <arquivo a ser monitorado>
```

**Status**
Para verificar o status das modificações feitas nos arquivos monitorados, basta o:

```shell
git status
```

**Remove (rm)**
Para remover um arquivo do monirtoramento e remover um arquivo, basta o comando:

```shell
git rm <arquivo>
```

**Commit**
Para salvar as mudanças feitos no código, temos o commando:

```shell
git commit -m "Messagem para o commit"
```

  Note que o _-m_ é para informar a mensagem do commit, caso não seja informado
  o git abrirá uma editor de texto para você esprecre uma mensagem mais longa,
  em que a 1º Linha é o titulo do commit, e o restante é o texto descritivo respectivamente.

Definições usadas pelo o Git:

* *HEAD* : Estado atual do nosso código, ou seja, onde o Git os colocou

* *Working tree* : Local onde os arquivos realmente estão sendo armazenados e editados

* *Index* : Local onde o Git armazena o que será commitado, ou seja, o local entre a working tree e o repositório Git em si.

**Log**
Para verificar o historico de modificações podemos usar o comando:

```shell
git log
```

Outra forma de verificar o log de commits:

Mostra historico em apenas uma linha por commit:

```shell
git log --oneline
git log -p
git log --graph
```

No site [devhints](https://devhints.io/git-log) tem uma boa explicação sobre

## Trabalhando com repositórios remotos

**Remote**
Adicionar um endereço remoto do git:

```shell
git remote add <Nome do endereço> <Pasta ou url>
```

Para verificar usa o comando:

```shell
git remote -v
```

   Em que o  caminha _fetch_ será de onde o código será buscado e o _push_ é o caminho para onde o código será mandado.

**Clone**
Para clonar um repositorio basta apenas:

```shell
git clone <Endereço do repositorio>
```

**Pull**
Para sincronizar e atualizar nosso projeto local com o remoto basta o camando:

```shell
git pull
```

Para enviar as mudanças feitas localmente para o repositorio remoto, usaremos o comanda:

```shell
git push <Nome do repositorio remoto> <Banch que deseja enviar>
```

## Trabalhando com Branchs

**Branch**
Para trabalhar com branchs basta usar o comando:

```shell
git branch - informas as branchs atuais
git branch <nome da branch> - cria uma nova branch
```

Para deletar uma branch:

```shell
git branch -D <Nome da branch>
```

**Checkout**
Para mudar de branch:

```shell
git checkout <nome da branch>
git checkout -b <Nome da branch> - cria e muda para a nova branch criada
```
Para voltar um arquivo ao estado anterior:

```shell
git checkout -- <Nome arquivo> - antes de commitar
```

Viagem no tempo usando o comando de mudanças:

```shell
git checkout <Hash do commit>
```

**Merge**
Para unir branchs criando um commit de merge:

```shell
git merge <Nome da branch> - fazerá a união da branch informada com a branch atual na qual está
```
**Rebase**
Para unir branchs sem criar um commit de merge:

```shell
git rebase <Nome da branch> - Não cria um commit de merge
```

**Revert**
Para reverter um commit feito usamos:

```shell
git revert <Hash do commit atual a ser revertido>
```

**Ordem para reverter alterações feitas**

```shell
git checkout - antes de adicionalas
git reset - antes de commitar
git revert - após commitar
```

**Stash**
Para salvar as mudanças feitas temporariamente usamos o:

```shell
git stash - salva a mudança
git stash list - mostra a lista de salvamentos
git stash apply [_Numero na lista_] - aplica a mudança feita
git stash drop - apaga a mudança salva
git stash pop - aplica a última alteração salva, e apaga
```

**Diff**
Mostra as mudanças feitas não salvas:

```shell
git diff
```

Mostra as mudanças feitas em um determinado commit:

```shell
  git diff <Hash do commit>
```
**Tag**
Adiciona uma tag atual:

```shell
git tag -a v0.1.0 -m "Menssagem na adição da tag"
```

Envia para o repositorio remoto a tag:

```shell
git push [_Repositorio remoto_] [_Tag a ser enviada_]
```

## Ao Infinito..... E além!

**Unindo commits**
Unindo vários commits em um só:

```shell
git rebase -i HEAD~<Número de commits>
```

Exemplo:
```shell
     git commit -i HEAD~3
```

<br/><center><strong>ou</strong></center><br/>

```shell
git rebase -i <Hash do commit anterior ao qual o começa a união>
```

Exemplo:

```shell
git commit -i 3bf3re3
```

* pick - Deixar
* s - Juntar

Após pedirá para você informar uma nova mensagem ao commit

**Cherry-pick**
Para pegar as mudanças feitas em um commit especifico e trazer ele para uma determinada branch atual, basta fazer o Cherry-pick, com o comando:

```shell
git cherry-pick <Hash do commit>
```

**Bisect**
Ver uma alteração feita em um commit especifico:

```shell
git bisect start -> Inicia a busca
git bisect bad HEAD -> Commit Atual
git bisect good <Hash do commit> -> Onde estava bom
git bisect bad -> se não encontrou o problema
git bisect good -> se encontrou o problema
git bisect reset -> para finalizar a busca
```

**Show**
Para mostrar tudo o que foi feito no commit, usa o comando:

```shell
git show <Hash do commit>
```

Para encontrar quem fez a alteração em um certo arquivo:

```shell
git blame <arquivo desejado>
```

#### Tópicos Indicados
Recomendo você dá uma pesquisada sobre os seguintes temas 😉:
* Gitflow
* Ferramentas Git visuais
* GitHooks