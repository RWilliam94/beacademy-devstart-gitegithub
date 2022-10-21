## NOME

git - o monitor de conteúdo estúpido

## RESUMO

```
git [--version] [--help] [-C <caminho>] [-c <nome>=<valor>]
    [--exec-path[=<caminho>]] [--html-path] [--man-path] [--info-path]
    [-p|--paginate|-P|--no-pager] [--no-replace-objects] [--bare]
    [--git-dir=<caminho>] [--work-tree=<caminho>] [--namespace=<nome>]
    [--super-prefix=<caminho>]
    <comando> [<args>]
```

## DESCRIÇÃO

O Git é um sistema de controle de revisão distribuído, rápido, escalável e com um conjunto de comandos incomumente rico que oferece operações de alto nível e acesso completo aos seus recursos.

Para começar, consulte [gittutorial[7\]](https://git-scm.com/docs/gittutorial/pt_BR) e depois [giteveryday[7\]](https://git-scm.com/docs/giteveryday/pt_BR) para conhecer um conjunto mínimo de comandos uteis. Para uma introdução mais aprofundada acesse o [Manual do Usuário do Git](https://git-scm.com/docs/user-manual/pt_BR).

Depois de dominar os conceitos básicos, é possível voltar para esta página para aprender quais os outros comandos o Git oferece. É possível aprender mais sobre os comandos individuais do Git com o comando "git help nome-do-comando". A página do manual [gitcli[7\]](https://git-scm.com/docs/gitcli/pt_BR) fornece uma visão geral da sintaxe de comandos da linha de comando.

Uma cópia formatada e com hiperlink da documentação mais recente do Git pode ser visualizada em https://git.github.io/htmldocs/git.html ou https://git-scm.com/docs.

## OPÇÕES

- --version

  Imprime a versão do pacote Git exibindo a sua origem.

- --help

  Imprime a sinopse e uma lista dos comandos mais usados. Caso a opção `--all` ou `-a` seja usada, todos os comandos disponíveis serão impressos. Caso um comando Git seja informado, esta opção exibirá a página do manual deste comando.Outras opções estão disponíveis para controlar como a página do manual é exibida. Para mais informações, consulte [git-help[1\]](https://git-scm.com/docs/git-help/pt_BR), pois o comando `git --help ...` é convertido internamente em `git help ...`.

- -C <caminho>

  Execute como se o git tivesse sido iniciado em *<caminho>* em vez do diretório de trabalho atual. Quando várias opções `-C` são usadas, cada `-C <caminho>` não absoluto subsequente é interpretado com relação ao `-C <caminho>` anterior. Se *<caminho>* estiver presente, porém vazio, por exemplo, `-C ""`, o diretório de trabalho atual permanecerá inalterado.Esta opção afeta as opções que esperam o nome do caminho, como `--git-dir` e `work-tree`, pois as suas interpretações dos nomes dos caminhos seriam feitas em relação ao diretório de trabalho causado pela opção `-C`. Como, por exemplo, as seguintes invocações são equivalentes:`git --git-dir=a.git --work-tree=b -C c status git --git-dir=c/a.git --work-tree=c/b status`

- -c <nome>=<valor>

  Encaminhe um parâmetro de configuração para o comando O valor informado substituirá os valores dos arquivos de configuração. Um `<nome>` é esperado no mesmo formato listado pelo comando *git config* (sub chaves separadas por pontos).Note que ao omitir `=` no comando `git -c foo.bar ...` é permitido e define `foo.bar` com o valor booleano verdadeiro (assim como`[foo]bar` faria em um arquivo de configuração). Incluindo os iguais, porém com um valor vazio (como `git -c foo.bar= ...`) define `foo.bar` para a string vazia que `git config --type=bool` converterá para `false`.

- --exec-path[=<caminho>]

  O caminho para onde os seus principais programas Git estão instalados. Isso também pode ser controlado configurando a variável de ambiente `GIT_EXEC_PATH`. Caso nenhum caminho seja informado, o *git* imprimirá a configuração atual e encerrará.

- --html-path

  Imprima o caminho, sem barra, onde a documentação HTML do Git está instalada e encerre.

- --man-path

  Imprima o manpath (consulte `man(1)`) para as páginas do manual desta versão do Git e encerre.

- --info-path

  Imprima o caminho onde os arquivos Info que documentam esta versão do Git estão instalados e encerre.

- -p

- --paginate

  Canalize toda a saída para *less* (ou caso esteja definido, `$PAGER`) caso a saída padrão seja um terminal. Isso substitui as opções de configuração `pager.<cmd>` (consulte a seção "Mecanismo de Configuração" abaixo).

- -p

- --no-pager

  Não canalize a saída do Git para um pager.

- --git-dir=<caminho>

  Define o caminho para o repositório (o diretório ".git"). Isso também pode ser controlado pela configuração da variável de ambiente `GIT_DIR`. Pode ser um caminho absoluto ou relativo ao diretório de trabalho atual.A especificação do local do diretório ".git" usando esta opção (ou a variável de ambiente `GIT_DIR`) desativa a descoberta do repositório que tenta localizar um diretório com o ".git" dentro (que é como o repositório e o nível mais alto da descoberta da árvore de trabalho) e informa ao Git que você está no nível mais alto da árvore de trabalho. Caso não esteja no diretório no nível mais alto da árvore de trabalho, deve informar ao Git onde está este nível da árvore de trabalho, com a opção `--work-tree=<caminho>` (ou a variável de ambiente `GIT_WORK_TREE`)Caso queira executar o git como se tivesse sido iniciado em `<caminho>`, utilize `git -C <caminho>`.

- --work-tree=<caminho>

  Define o caminho para a árvore de trabalho. Pode ser um caminho absoluto ou relativo ao diretório de trabalho atual. Também pode ser controlado atrvés da configuração da variável de ambiente `GIT_WORK_TREE` e da variável de configuração `core.worktree` (consulte `core.worktree` no [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR) para uma discussão com mais detalhes).

- --namespace=<caminho>

  Define o espaço de nomes no Git. Para mais detalhes consulte [gitnamespaces[7\]](https://git-scm.com/docs/gitnamespaces/pt_BR). É o mesmo que configurar a variável de ambiente `GIT_NAMESPACE`.

- --super-prefix=<caminho>

  Apenas para uso interno. Set a prefix which gives a path from above a repository down to its root. One use is to give submodules context about the superproject that invoked it.

- --bare

  Trate o repositório como um repositório simples. Caso o ambiente `GIT_DIR` não estiver definido, ele será definido no diretório de trabalho atual.

- --no-replace-objects

  Não utilize substituições "ref" para substituir os objetos Git. Para mais informações consulte [git-replace[1\]](https://git-scm.com/docs/git-replace/pt_BR).

- --literal-pathspecs

  Trate os pathspecs literalmente (ou seja, sem "globbing", sem a magia do "pathspec"). É o mesmo que definir a variável de ambiente `GIT_LITERAL_PATHSPECS` como `1`.

- --glob-pathspecs

  Adicione a magia *glob* para todos os *pathspec*. É como definir a variável de ambiente `GIT_GLOB_PATHSPECS` como `1`. A desativação do caractere curinga nos pathspecs individuais podem ser feitos utilizando a mágica do pathspec ": (literal)"

- --noglob-pathspecs

  Adicione a magia *literal* a todos os "pathspec". É equivalente a definir a variável de ambiente `GIT_NOGLOB_PATHSPECS` para `1`. A ativação dos caracteres curinga nos "pathspecs" individuais podem ser feitos utilizando a mágica do pathspec ":(glob)"

- --icase-pathspecs

  Adicione a magia *icase* em todos os pathspec. É como definir a variável de ambiente `GIT_ICASE_PATHSPECS` como `1`.

- --no-optional-locks

  Não execute operações opcionais que exijam bloqueios. Isso é equivalente que definir o `GIT_OPTIONAL_LOCKS` como `0`.

- --list-cmds=group[,group…]

  Liste os comandos por grupo. Essa é uma opção interna/experimental e pode mudar ou ser removido no futuro. Os grupos compatíveis são: `builtins`, `parseopt` (comandos internos que utilizam *parse-options´), `main` (todos os comandos no diretório 'libexec*), `others` (todos os outros comandos no `$PATH` que possuem um prefixo git), `list- <categoria>` (consulte as categorias no *command-list.txt*), `nohelpers` (exclua os comandos auxiliares), `alias` e `config` (recupera a lista dos comandos da variável `completion.commands`)

## OS COMANDOS DO GIT

Dividimos o Git em comandos de alto nível ("porcelana") e de baixo nível ("encanamento").

## Comandos de alto nível (porcelana)

Separamos os comandos porcelana nos comandos principais e em alguns utilitários auxiliares do usuário.

### Os principais comandos porcelana

- [git-add[1\]](https://git-scm.com/docs/git-add/pt_BR)

  Adiciona o conteúdo dos arquivos ao índice.

- [git-am[1\]](https://git-scm.com/docs/git-am/pt_BR)

  Aplica uma série de patches vindos de uma caixa de e-mails.

- [git-archive[1\]](https://git-scm.com/docs/git-archive/pt_BR)

  Cria um histórico dos arquivos a partir de uma determinada árvore.

- [git-bisect[1\]](https://git-scm.com/docs/git-bisect/pt_BR)

  Utilize a procura binária para localizar o commit que introduziu um bug.

- [git-branch[1\]](https://git-scm.com/docs/git-branch/pt_BR)

  Lista, cria ou exclui os ramos.

- [git-bundle[1\]](https://git-scm.com/docs/git-bundle/pt_BR)

  Mova os objetos e as refs através do histórico.

- [git-checkout[1\]](https://git-scm.com/docs/git-checkout/pt_BR)

  Mova os ramos ou restaura os arquivos da árvores de trabalho.

- [git-cherry-pick[1\]](https://git-scm.com/docs/git-cherry-pick/pt_BR)

  Aplica as mudanças introduzidas por alguns commits já existentes.

- [git-citool[1\]](https://git-scm.com/docs/git-citool/pt_BR)

  Uma alternativa gráfica ao git-commit.

- [git-clean[1\]](https://git-scm.com/docs/git-clean/pt_BR)

  Remove os arquivos da árvore de trabalho sem monitoramento.

- [git-clone[1\]](https://git-scm.com/docs/git-clone/pt_BR)

  Clona um repositório em um novo diretório.

- [git-commit[1\]](https://git-scm.com/docs/git-commit/pt_BR)

  Grava as alterações para o repositório.

- [git-describe[1\]](https://git-scm.com/docs/git-describe/pt_BR)

  Dá a um objeto um nome em um formato legível para humanos com base em um "ref" disponível.

- [git-diff[1\]](https://git-scm.com/docs/git-diff/pt_BR)

  Exiba as alterações entre os commits, o commit, árvore de trabalho, etc.

- [git-fetch[1\]](https://git-scm.com/docs/git-fetch/pt_BR)

  Faz o download dos objetos e dos refs vindo de outro repositório.

- [git-format-patch[1\]](https://git-scm.com/docs/git-format-patch/pt_BR)

  Prepara os patches para serem enviados por e-mail.

- [git-gc[1\]](https://git-scm.com/docs/git-gc/pt_BR)

  Exclui os arquivos desnecessários e otimiza o repositório local.

- [git-grep[1\]](https://git-scm.com/docs/git-grep/pt_BR)

  Imprima as linhas que coincidam com um padrão.

- [git-gui[1\]](https://git-scm.com/docs/git-gui/pt_BR)

  Uma interface gráfica portátil para o Git.

- [git-init[1\]](https://git-scm.com/docs/git-init/pt_BR)

  Cria um repositório vazio para o Git ou reinicializa um repositório já existente.

- [git-log[1\]](https://git-scm.com/docs/git-log/pt_BR)

  Exibe os registros logs de um commit.

- [git-merge[1\]](https://git-scm.com/docs/git-merge/pt_BR)

  Une dois ou mais históricos de desenvolvimento juntos.

- [git-mv[1\]](https://git-scm.com/docs/git-mv/pt_BR)

  Move ou renomeia um arquivo, um diretório ou um link simbólico.

- [git-notes[1\]](https://git-scm.com/docs/git-notes/pt_BR)

  Adiciona ou inspeciona as anotações dos objetos.

- [git-pull[1\]](https://git-scm.com/docs/git-pull/pt_BR)

  Capture de e o integre com um outro repositório ou em um outro ramo local.

- [git-push[1\]](https://git-scm.com/docs/git-push/pt_BR)

  Atualiza os refs remotos através da associação dos objetos.

- [git-range-diff[1\]](https://git-scm.com/docs/git-range-diff/pt_BR)

  Compara os dois intervalos de um commit (duas versões de um ramo por exemplo).

- [git-rebase[1\]](https://git-scm.com/docs/git-rebase/pt_BR)

  Reaplica os commits no topo do outro cume da base.

- [git-reset[1\]](https://git-scm.com/docs/git-reset/pt_BR)

  Redefine o HEAD atual para o para a condição determinada.

- [git-restore[1\]](https://git-scm.com/docs/git-restore/pt_BR)

  Restaura as árvores de trabalho.

- [git-revert[1\]](https://git-scm.com/docs/git-revert/pt_BR)

  Reverte alguns commits já existentes.

- [git-rm[1\]](https://git-scm.com/docs/git-rm/pt_BR)

  Remove os arquivos da árvore de trabalho e do índice.

- [git-shortlog[1\]](https://git-scm.com/docs/git-shortlog/pt_BR)

  Faça um resumo da saída do *git log*.

- [git-show[1\]](https://git-scm.com/docs/git-show/pt_BR)

  Exiba os vários tipos de objetos.

- [git-sparse-checkout[1\]](https://git-scm.com/docs/git-sparse-checkout/pt_BR)

  Alter e inicialize a averiguação esparsa.

- [git-stash[1\]](https://git-scm.com/docs/git-stash/pt_BR)

  Armazene as alterações em um diretório fora do diretório de trabalho.

- [git-status[1\]](https://git-scm.com/docs/git-status/pt_BR)

  Exiba a condição atual da árvore de trabalho.

- [git-submodule[1\]](https://git-scm.com/docs/git-submodule/pt_BR)

  Inicializa, atualiza ou inspeciona submódulos.

- [git-switch[1\]](https://git-scm.com/docs/git-switch/pt_BR)

  Alterna entre os ramos.

- [git-tag[1\]](https://git-scm.com/docs/git-tag/pt_BR)

  Cria, lista, exclui ou verifica uma tag do objeto com assinatura GPG.

- [git-worktree[1\]](https://git-scm.com/docs/git-worktree/pt_BR)

  Manipula as diversas árvores de trabalho.

- [gitk[1\]](https://git-scm.com/docs/gitk/pt_BR)

  O navegador do repositório Git.

### Comandos Auxiliares

Manipuladores:

- [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR)

  Obtém e define os repositórios ou as opções globais.

- [git-fast-export[1\]](https://git-scm.com/docs/git-fast-export/pt_BR)

  Exportador de dados do Git.

- [git-fast-import[1\]](https://git-scm.com/docs/git-fast-import/pt_BR)

  Estrutura para os importadores de dados rápidos do Git.

- [git-filter-branch[1\]](https://git-scm.com/docs/git-filter-branch/pt_BR)

  Reescreve os ramos.

- [git-mergetool[1\]](https://git-scm.com/docs/git-mergetool/pt_BR)

  Executa as ferramentas de resolução problemas para resolver os conflitos de mesclagem.

- [git-pack-refs[1\]](https://git-scm.com/docs/git-pack-refs/pt_BR)

  Empacota os cabeçalhos e as tags para um acesso eficiente ao repositório.

- [git-prune[1\]](https://git-scm.com/docs/git-prune/pt_BR)

  Corta todos os objetos fora de alcance do banco de dados de objetos.

- [git-reflog[1\]](https://git-scm.com/docs/git-reflog/pt_BR)

  Gerencia as informações do reflog.

- [git-remote[1\]](https://git-scm.com/docs/git-remote/pt_BR)

  Gerencia o conjunto de repositórios monitorados.

- [git-repack[1\]](https://git-scm.com/docs/git-repack/pt_BR)

  Empacota os objetos não empacotados em um repositório.

- [git-replace[1\]](https://git-scm.com/docs/git-replace/pt_BR)

  Cria, lista e exclui os refs para a reposição dos objetos.

Interrogadores:

- [git-annotate[1\]](https://git-scm.com/docs/git-annotate/pt_BR)

  Anota as linhas com as informações do commit.

- [git-blame[1\]](https://git-scm.com/docs/git-blame/pt_BR)

  Exibe quais foram as últimas modificações feitas em cada linha de um arquivo separados pela versão da revisão e do autor da modificação.

- [git-bugreport[1\]](https://git-scm.com/docs/git-bugreport/pt_BR)

  Colete informações para que o usuário envie um relatório de erro.

- [git-count-objects[1\]](https://git-scm.com/docs/git-count-objects/pt_BR)

  Conta a quantidade dos objetos que não foram empacotados e seu consumo no disco.

- [git-difftool[1\]](https://git-scm.com/docs/git-difftool/pt_BR)

  Exibe as mudanças utilizando ferramentas diff tradicionais.

- [git-fsck[1\]](https://git-scm.com/docs/git-fsck/pt_BR)

  Verifica a conectividade e validade dos objetos em um banco de dados.

- [git-help[1\]](https://git-scm.com/docs/git-help/pt_BR)

  Exiba a informação de ajuda sobre o Git.

- [git-instaweb[1\]](https://git-scm.com/docs/git-instaweb/pt_BR)

  Navegue instantaneamente no seu repositório de trabalho com o gitweb.

- [git-merge-tree[1\]](https://git-scm.com/docs/git-merge-tree/pt_BR)

  Exiba as três maneiras de mesclagem sem mexer no índice.

- [git-rerere[1\]](https://git-scm.com/docs/git-rerere/pt_BR)

  Reutilize uma resolução gravada das mesclagens conflitantes.

- [git-show-branch[1\]](https://git-scm.com/docs/git-show-branch/pt_BR)

  Exiba os ramos e seus respectivos commits.

- [git-verify-commit[1\]](https://git-scm.com/docs/git-verify-commit/pt_BR)

  Verifique a assinatura GPG dos commits.

- [git-verify-tag[1\]](https://git-scm.com/docs/git-verify-tag/pt_BR)

  Verifique a assinatura GPG das tags.

- [git-whatchanged[1\]](https://git-scm.com/docs/git-whatchanged/pt_BR)

  Exiba os registros logs com a diferença entre a introdução de cada commit.

- [gitweb[1\]](https://git-scm.com/docs/gitweb/pt_BR)

  Interface web do Git (frontend web para os repositórios Git).

### Interagindo com os outros

Estes comandos são para interagir com um SCM externo e com as outras pessoas através de patch por e-mail.

- [git-archimport[1\]](https://git-scm.com/docs/git-archimport/pt_BR)

  Importa um repositório GNU Arch no Git.

- [git-cvsexportcommit[1\]](https://git-scm.com/docs/git-cvsexportcommit/pt_BR)

  Exporta um único commit para uma averiguação do CVS.

- [git-cvsimport[1\]](https://git-scm.com/docs/git-cvsimport/pt_BR)

  Recupera os seus dados vindos de outros SCM que as pessoas adoram odiar.

- [git-cvsserver[1\]](https://git-scm.com/docs/git-cvsserver/pt_BR)

  Um emulador de um servidor CVS para o Git.

- [git-imap-send[1\]](https://git-scm.com/docs/git-imap-send/pt_BR)

  Envia uma coleção de patches da entrada padrão para um diretório IMAP.

- [git-p4[1\]](https://git-scm.com/docs/git-p4/pt_BR)

  Importa de e submete aos repositório Perforce.

- [git-quiltimport[1\]](https://git-scm.com/docs/git-quiltimport/pt_BR)

  Aplica um conjunto de patches no ramo atual.

- [git-request-pull[1\]](https://git-scm.com/docs/git-request-pull/pt_BR)

  Gera um resumo com as modificações pendentes.

- [git-send-email[1\]](https://git-scm.com/docs/git-send-email/pt_BR)

  Envia uma coleção de patches como sendo e-mails.

- [git-svn[1\]](https://git-scm.com/docs/git-svn/pt_BR)

  Operação bidirecional entre um repositório do Subversion e do Git.

### Redefina, restaure e reverta

Existem três comandos com nomes semelhantes: `git reset`, `git restore` e o `git revert`.

- [git-revert[1\]](https://git-scm.com/docs/git-revert/pt_BR) trata de fazer um novo commit que reverte as alterações feitas por outros commit.

- [git-restore[1\]](https://git-scm.com/docs/git-restore/pt_BR) trata da restauração dos arquivos na árvore de trabalho do índice ou de outro commit. Este comando não atualiza o seu ramo. O comando também pode ser usado para restaurar os arquivos no índice do outro commit.

- [git-reset[1\]](https://git-scm.com/docs/git-reset/pt_BR) trata da atualização do seu ramo, movendo o topo para adicionar ou remover os commits do ramo. Esta operação altera o histórico do commit.

  O comando `git reset` também pode ser usado para restaurar o índice, sobrepondo com `git restore`.

## Comandos de baixo nível (encanamento *plumbing*)

Embora o Git inclua a sua própria camada de porcelana, os seus comandos de baixo nível são suficientes para apoiar o desenvolvimento de porcelanas alternativas. Os desenvolvedores destas porcelanas podem começar lendo sobre [git-update-index[1\]](https://git-scm.com/docs/git-update-index/pt_BR) e [git-read-tree[1\]](https://git-scm.com/docs/git-read-tree/pt_BR).

A interface (entrada, saída, conjunto de opções e as semânticas) para esses comandos de baixo nível deve ser muito mais estável que os comandos porcelana, porque estes comandos são principalmente para uso com um script. A interface para os comandos Porcelana, por outro lado, está sujeita a alterações para melhorar a experiência do usuário final.

A descrição a seguir divide os comandos de baixo nível em comandos que manipulam os objetos (no repositório, índice e árvore de trabalho), comandos que interrogam, comparam objetos, comandos que movem objetos e suas referências entre os repositórios.

### Comandos de manipulação

- [git-apply[1\]](https://git-scm.com/docs/git-apply/pt_BR)

  Aplique um patch nos arquivos e/ou ao índice.

- [git-checkout-index[1\]](https://git-scm.com/docs/git-checkout-index/pt_BR)

  Copie os arquivos do índice para a árvore de trabalho.

- [git-commit-graph[1\]](https://git-scm.com/docs/git-commit-graph/pt_BR)

  Escreve e verifica os arquivos `commit-graph` do Git.

- [git-commit-tree[1\]](https://git-scm.com/docs/git-commit-tree/pt_BR)

  Cria um novo objeto commit.

- [git-hash-object[1\]](https://git-scm.com/docs/git-hash-object/pt_BR)

  Calcula o ID do objeto e opcionalmente cria uma bolha vinda de um arquivo.

- [git-index-pack[1\]](https://git-scm.com/docs/git-index-pack/pt_BR)

  Constrói um pacote índice do arquivo para um arquivo de pacote já existente.

- [git-merge-file[1\]](https://git-scm.com/docs/git-merge-file/pt_BR)

  Execute a mesclagem de um arquivo de três vias.

- [git-merge-index[1\]](https://git-scm.com/docs/git-merge-index/pt_BR)

  Execute uma mesclagem para os arquivos que precisam ser mesclados.

- [git-mktag[1\]](https://git-scm.com/docs/git-mktag/pt_BR)

  Cria um objeto tag.

- [git-mktree[1\]](https://git-scm.com/docs/git-mktree/pt_BR)

  Cria uma árvore-objeto de um texto com formatação `ls-tree`.

- [git-multi-pack-index[1\]](https://git-scm.com/docs/git-multi-pack-index/pt_BR)

  Escreve e verifica os diversos índices dos pacotes.

- [git-pack-objects[1\]](https://git-scm.com/docs/git-pack-objects/pt_BR)

  Cria um histórico empacotado dos objetos.

- [git-prune-packed[1\]](https://git-scm.com/docs/git-prune-packed/pt_BR)

  Remove os objetos extras que estejam atualmente nos arquivos empacotados.

- [git-read-tree[1\]](https://git-scm.com/docs/git-read-tree/pt_BR)

  Lê a informação da árvore no índice.

- [git-symbolic-ref[1\]](https://git-scm.com/docs/git-symbolic-ref/pt_BR)

  Lê, modifica e exclui os refs simbólicos.

- [git-unpack-objects[1\]](https://git-scm.com/docs/git-unpack-objects/pt_BR)

  Desempacota os objetos de um arquivo empacotado.

- [git-update-index[1\]](https://git-scm.com/docs/git-update-index/pt_BR)

  Registra o conteúdo de um arquivo na árvore de trabalho para o índice.

- [git-update-ref[1\]](https://git-scm.com/docs/git-update-ref/pt_BR)

  Atualiza o nome do objeto armazenado em um "ref" de forma segura.

- [git-write-tree[1\]](https://git-scm.com/docs/git-write-tree/pt_BR)

  Cria um objeto árvore com base no índice atual.

### Comandos de interrogação

- [git-cat-file[1\]](https://git-scm.com/docs/git-cat-file/pt_BR)

  Proporciona o conteúdo, o tipo e a informação sobre o tamanho dos objetos no repositório.

- [git-cherry[1\]](https://git-scm.com/docs/git-cherry/pt_BR)

  Procura os commits que ainda serão aplicados ao "upstream".

- [git-diff-files[1\]](https://git-scm.com/docs/git-diff-files/pt_BR)

  Compara os arquivos na árvore de trabalho e no índice.

- [git-diff-index[1\]](https://git-scm.com/docs/git-diff-index/pt_BR)

  Compara uma árvore com o diretório de trabalho ou índice.

- [git-diff-tree[1\]](https://git-scm.com/docs/git-diff-tree/pt_BR)

  Compara o conteúdo e o modo das bolhas encontrados através de dois objetos da árvore.

- [git-for-each-ref[1\]](https://git-scm.com/docs/git-for-each-ref/pt_BR)

  Informação de saída de cada "ref".

- [git-get-tar-commit-id[1\]](https://git-scm.com/docs/git-get-tar-commit-id/pt_BR)

  Extrai o ID do commit de um arquivo criado utilizando o *git-archive*.

- [git-ls-files[1\]](https://git-scm.com/docs/git-ls-files/pt_BR)

  Exiba a informação sobre os arquivos no índice e na árvore de trabalho.

- [git-ls-remote[1\]](https://git-scm.com/docs/git-ls-remote/pt_BR)

  Lista as referências em um repositório remoto.

- [git-ls-tree[1\]](https://git-scm.com/docs/git-ls-tree/pt_BR)

  Lista o conteúdo de uma árvore de objetos.

- [git-merge-base[1\]](https://git-scm.com/docs/git-merge-base/pt_BR)

  Localize os melhores ancestrais possíveis para fazer uma mesclagem.

- [git-name-rev[1\]](https://git-scm.com/docs/git-name-rev/pt_BR)

  Localize os nomes simbólicos para os "revs" que foram informados.

- [git-pack-redundant[1\]](https://git-scm.com/docs/git-pack-redundant/pt_BR)

  Localiza os arquivos "pack" que forem redundantes.

- [git-rev-list[1\]](https://git-scm.com/docs/git-rev-list/pt_BR)

  Lista os objetos de commit em ordem cronológica reversa.

- [git-rev-parse[1\]](https://git-scm.com/docs/git-rev-parse/pt_BR)

  Escolha e modele os parâmetros.

- [git-show-index[1\]](https://git-scm.com/docs/git-show-index/pt_BR)

  Exiba o índice do arquivo empacotado.

- [git-show-ref[1\]](https://git-scm.com/docs/git-show-ref/pt_BR)

  Lista as referências em um repositório local.

- [git-unpack-file[1\]](https://git-scm.com/docs/git-unpack-file/pt_BR)

  Cria um arquivo temporário com conteúdos bolha.

- [git-var[1\]](https://git-scm.com/docs/git-var/pt_BR)

  Exiba uma variável lógica local para o Git.

- [git-verify-pack[1\]](https://git-scm.com/docs/git-verify-pack/pt_BR)

  Valide os arquivos empacotados do Git.

Em geral, os comandos de interrogação não tocam nos arquivos da árvore de trabalho.

### Sincronizando os repositórios

- [git-daemon[1\]](https://git-scm.com/docs/git-daemon/pt_BR)

  Um servidor realmente simples para os repositórios Git.

- [git-fetch-pack[1\]](https://git-scm.com/docs/git-fetch-pack/pt_BR)

  Recebe os objetos que faltam de um outro repositório.

- [git-http-backend[1\]](https://git-scm.com/docs/git-http-backend/pt_BR)

  Implementação do lado do servidor do Git através do HTTP.

- [git-send-pack[1\]](https://git-scm.com/docs/git-send-pack/pt_BR)

  impulsiona os objetos sob o protocolo Git de um outro repositório.

- [git-update-server-info[1\]](https://git-scm.com/docs/git-update-server-info/pt_BR)

  Atualiza a informação auxiliar sobre o arquivo para ajudar os servidores burros.

A seguir, são apresentados os comandos auxiliares utilizados acima; os usuários finais normalmente não os utilizam diretamente.

- [git-http-fetch[1\]](https://git-scm.com/docs/git-http-fetch/pt_BR)

  Faz o download de um repositório remoto Git através do HTTP.

- [git-http-push[1\]](https://git-scm.com/docs/git-http-push/pt_BR)

  Impulsiona (push) os objetos através do HTTP/DAV para um outro repositório.

- [git-parse-remote[1\]](https://git-scm.com/docs/git-parse-remote/pt_BR)

  Rotinas para auxiliar na analise dos parâmetros de acesso ao repositório remoto.

- [git-receive-pack[1\]](https://git-scm.com/docs/git-receive-pack/pt_BR)

  Receba o que é impulsionado ao repositório.

- [git-shell[1\]](https://git-scm.com/docs/git-shell/pt_BR)

  Shell de login restrito para acesso somente com o SSH do Git.

- [git-upload-archive[1\]](https://git-scm.com/docs/git-upload-archive/pt_BR)

  Envia um arquivo de volta ao `git-archive`.

- [git-upload-pack[1\]](https://git-scm.com/docs/git-upload-pack/pt_BR)

  Envia os objetos compactados para o `git-fetch-pack`.

### Comandos auxiliares internos

Estes são comandos auxiliares internos usados por outros comandos; os usuários finais normalmente não os utilizam diretamente.

- [git-check-attr[1\]](https://git-scm.com/docs/git-check-attr/pt_BR)

  Exiba a informação do `gitattributes`.

- [git-check-ignore[1\]](https://git-scm.com/docs/git-check-ignore/pt_BR)

  Depure o gitignore / exclua os arquivos.

- [git-check-mailmap[1\]](https://git-scm.com/docs/git-check-mailmap/pt_BR)

  Exiba os nomes canônicos e os endereços de e-mail dos contatos.

- [git-check-ref-format[1\]](https://git-scm.com/docs/git-check-ref-format/pt_BR)

  Certifique que um nome de uma referência está bem formado.

- [git-column[1\]](https://git-scm.com/docs/git-column/pt_BR)

  Exiba os dados em colunas.

- [git-credential[1\]](https://git-scm.com/docs/git-credential/pt_BR)

  Obtém e guarda as credenciais dos usuários.

- [git-credential-cache[1\]](https://git-scm.com/docs/git-credential-cache/pt_BR)

  Auxiliar para armazenar as senhas temporariamente na memória.

- [git-credential-store[1\]](https://git-scm.com/docs/git-credential-store/pt_BR)

  Auxiliar para armazenar as credenciais no disco.

- [git-fmt-merge-msg[1\]](https://git-scm.com/docs/git-fmt-merge-msg/pt_BR)

  Gera uma mensagem de mesclagem do commit.

- [git-interpret-trailers[1\]](https://git-scm.com/docs/git-interpret-trailers/pt_BR)

  Adiciona ou analisa as informações estruturadas nas mensagens do commit.

- [git-mailinfo[1\]](https://git-scm.com/docs/git-mailinfo/pt_BR)

  Extrai a correção e o autor de uma única mensagem de e-mail.

- [git-mailsplit[1\]](https://git-scm.com/docs/git-mailsplit/pt_BR)

  Programa simples para dividir o mbox UNIX.

- [git-merge-one-file[1\]](https://git-scm.com/docs/git-merge-one-file/pt_BR)

  O programa assistente predefinido de ajuda para usar com o `git-merge-index`.

- [git-patch-id[1\]](https://git-scm.com/docs/git-patch-id/pt_BR)

  Compute um ID único para um patch.

- [git-sh-i18n[1\]](https://git-scm.com/docs/git-sh-i18n/pt_BR)

  Código da configuração do i18n do Git para scripts shell.

- [git-sh-setup[1\]](https://git-scm.com/docs/git-sh-setup/pt_BR)

  Código da configuração comum do script shell do Git.

- [git-stripspace[1\]](https://git-scm.com/docs/git-stripspace/pt_BR)

  Remove os espaços desnecessários.

## Mecanismo de Configuração

O Git utiliza um formato de texto simples para armazenar as personalizações por repositório e por usuário. Tal arquivo de configuração pode ficar assim:

```
#
# Os caracteres '#' ou ';' indicam um comentário.
#

; variáveis principais
[core]
	; Não confie nos modos dos arquivos
	filemode = false

; identidade do usuário
[user]
	name = "Junio C Hamano"
	email = "gitster@pobox.com"
```

Vários comandos são lidos no arquivo de configuração e ajustam a sua operação de acordo. Para obter uma lista e mais detalhes sobre o mecanismo de configuração, consulte [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR).

## Terminologia do Identificador

- <objeto>

  Indica o nome do objeto para qualquer tipo de objeto.

- <blob>

  Indica um nome de um objeto bolha.

- <árvore>

  Indica um nome de um objeto árvore.

- <commit>

  Indica um nome de um objeto commit.

- <tree-ish>

  Indica uma árvore, nome de um objeto commit ou tag. Um comando que aceite um argumento <commit-ish> e queira operar em um objeto <commit>, porém remove a referência automaticamente dos objetos <tag> que apontem para um <commit>.

- <commit-ish>

  Indica um nome do objeto commit ou tag. Um comando que aceita um argumento <commit-ish> e queira operar em um objeto <commit>, porém remove a referência automaticamente dos objetos <tag> que apontem para um <commit>.

- <tipo>

  Indica que um tipo do objeto seja necessário. Atualmente um dos: `blob`, `tree`, `commit`, ou `tag`.

- <arquivo>

  Indica um nome do arquivo - quase sempre em relação à raiz da estrutura da árvore que o `GIT_INDEX_FILE` descreve.

## Identificadores Simbólicos

Qualquer comando Git que aceite qualquer <objeto> também pode utilizar a seguinte notação simbólica:

- HEAD

  indica o cabeçalho do ramo atual.

- <tag>

  uma tag válida *nome* (como, por exemplo, uma referência `refs/tags/<tag>`).

- <head>

  um cabeçalho válido *nome* (como, por exemplo, uma referência `refs/heads/<head>`).

Para obter uma lista mais completa de maneiras de soletrar os nomes dos objetos, consulte a seção "DEFININDO AS REVISÕES" em [gitrevisions[7\]](https://git-scm.com/docs/gitrevisions/pt_BR).

## A Estrutura dos Arquivos/Diretórios

Favor consultar o documento [gitrepository-layout[5\]](https://git-scm.com/docs/gitrepository-layout/pt_BR).

Para mais detalhes sobre cada gancho, consulte [githooks[5\]](https://git-scm.com/docs/githooks/pt_BR).

Os SCMs de alto nível podem fornecer e gerenciar informações adicionais no `$GIT_DIR`.

## Terminologia

Favor consultar [gitglossary[7\]](https://git-scm.com/docs/gitglossary/pt_BR).

## As Variáveis do Ambiente

Vários comandos Git usam as seguintes variáveis de ambiente:

### O Repositório Git

Essas variáveis de ambiente se aplicam a *todos* os comandos principais do Git. Nb: é importante notar que eles podem ser usados/substituídos pelo SCMS acima do Git, portanto, tenha cuidado caso esteja usando um front-end externo.

- `GIT_INDEX_FILE`

  Este ambiente permite a definição de um arquivo índice alternativo. Caso não seja definido, a predefinição do `$GIT_DIR/index` é utilizado.

- `GIT_INDEX_VERSION`

  Essa variável de ambiente permite a especificação de uma versão de índice para os novos repositórios. Não afetará os arquivos de índice existentes. Por predefinição, a versão 2 ou 3 do arquivo de índice é utilizado. Para mais informações consulte [git-update-index[1\]](https://git-scm.com/docs/git-update-index/pt_BR).

- `GIT_OBJECT_DIRECTORY`

  Caso o diretório de armazenamento dos objetos seja informado através desta variável de ambiente, os diretórios sha1 serão criados embaixo - caso contrário, o diretório predefinido `$GIT_DIR/objects` será utilizado.

- `GIT_ALTERNATE_OBJECT_DIRECTORIES`

  Devido à natureza imutável dos objetos Git, os objetos antigos podem ser arquivados em diretórios compartilhados com somente leitura apenas. Esta variável especifica uma lista ":" separada (no Windows ";") dos diretórios dos objetos Git que podem ser utilizados para localizar objetos Git. Os novos objetos não serão gravados nestes diretórios.As entradas que começam com `"` (aspas duplas) serão interpretadas como caminhos entre as aspas no estilo C, removendo as aspas duplas iniciais e finais, respeitando as escapes da barra invertida. Como por exemplo, o valor `"path-with-\"-and-:-in-it":vanilla-path` possuí dois caminhos: `path-with-"-and-:-in-it` e `vanilla-path`.

- `GIT_DIR`

  Caso a variável de ambiente `GIT_DIR` esteja definida, ela definirá um caminho que será utilizado em vez do `.git` predefinido como sendo a base do repositório. A opção da linha de comando `--git-dir` também define este valor.

- `GIT_WORK_TREE`

  Defina o caminho para a raiz da árvore de trabalho. Isso também pode ser controlado pela opção da linha de comando `--work-tree` e pela variável de configuração `core.worktree`.

- `GIT_NAMESPACE`

  Define o espaço de nomes no Git; para mais detalhes consulte [gitnamespaces[7\]](https://git-scm.com/docs/gitnamespaces/pt_BR). A opção da linha de comando `--namespace` também define este valor.

- `GIT_CEILING_DIRECTORIES`

  Essa deve ser uma lista separada por dois pontos com caminhos absolutos. Caso seja definido, é uma lista dos diretórios onde o Git não deve mudar de diretório (chdir) enquanto procura um diretório do repositório (útil para excluir os diretórios da rede com carregamento lento). Ele não excluirá o diretório de trabalho atual, um `GIT_DIR` definido na linha de comandos ou no ambiente. Normalmente, o Git precisa ler as entradas nesta lista e resolver qualquer link simbólico que possa estar presente para compará-las com o diretório atual. No entanto, mesmo que esse acesso seja lento, você pode adicionar uma entrada vazia à lista para informar ao Git que as entradas subsequentes não são links simbólicos e não precisam ser resolvidos; como, por exemplo, `GIT_CEILING_DIRECTORIES=/maybe/symlink::/very/slow/non/symlink`.

- `GIT_DISCOVERY_ACROSS_FILESYSTEM`

  Quando executado em um diretório que não possui o diretório do repositório ".git", o Git tenta encontrar esse diretório nos diretórios pais para encontrar o cume da árvore de trabalho, porém, é predefinido que, ele não cruze os limites do sistema de arquivos. Essa variável de ambiente pode ser configurada como *true* para dizer ao Git para não parar nos limites do sistema de arquivos. Como o `GIT_CEILING_DIRECTORIES`, isso não afetará explicitamente um diretório do repositório definido através do `GIT_DIR` ou na linha de comando.

- `GIT_COMMON_DIR`

  Se essa variável estiver definida para um caminho, os arquivos que não são da árvore de trabalho, estão normalmente estão em $GIT_DIR e serão obtidos desse caminho. Os arquivos específicos da árvore de trabalho, como `HEAD` ou índice serão obtidos de $GIT_DIR. Para mais detalhes consulte [gitrepository-layout[5\]](https://git-scm.com/docs/gitrepository-layout/pt_BR) e [git-worktree[1\]](https://git-scm.com/docs/git-worktree/pt_BR). Essa variável tem precedência mais baixa do que outras variáveis de caminho como `GIT_INDEX_FILE`, `GIT_OBJECT_DIRECTORY`…

- `GIT_DEFAULT_HASH`

  Caso esta variável esteja definida, o algoritmo hash predefinido para os novos repositórios será definido com este valor. Este valor é atualmente ignorado durante a clonagem; em vez disso, a configuração do repositório remoto é utilizada. O valor predefinido é `sha1`.

### Os Commits do Git

- `GIT_AUTHOR_NAME`

  O endereço legível do endereço de e-mail utilizado na identidade do autor ao criar os commits, na tag dos objetos ou ao gravar os reflogs. Substitui as definições de configuração `user.name` e `author.name`.

- `GIT_AUTHOR_EMAIL`

  O endereço de email utilizado na identidade do autor ao criar os commits, na marcação dos objetos ou ao gravar os reflogs. Substitui as definições da configuração `user.email` e `author.email`.

- `GIT_AUTHOR_DATE`

  A data utilizada para a identidade do autor ao criar objetos commit ou tags ou quando escrever "reflogs". Para conhecer os formatos válidos, consulte [git-commit[1\]](https://git-scm.com/docs/git-commit/pt_BR).

- `GIT_COMMITTER_NAME`

  O endereço legível do nome utilizado na identidade do autor do commit ao criar os commits, na tag dos objetos ou ao gravar os reflogs. Substitui as definições de configuração `user.name` e `committer.name`.

- `GIT_COMMITTER_EMAIL`

  O endereço de email utilizado na identidade do autor ao criar os commits, na marcação dos objetos ou ao gravar os reflogs. Overrides the `user.email` and `committer.email` configuration settings.

- `GIT_COMMITTER_DATE`

  A data utilizada para a identidade de quem fez o commit durante a criação dos objetos as tags do commit ou ao gravar os reflogs. Para mais formatos válidos, consulte [git-commit[1\]](https://git-scm.com/docs/git-commit/pt_BR).

- `EMAIL`

  O endereço de e-mail usado nas identidades do autor e do commit, caso nenhuma outra variável de ambiente ou da configuração relevante tiver sido definida.

### Os Diffs do Git

- `GIT_DIFF_OPTS`

  A única opção válida é "--unified=??" ou "-u??" para definir o número de linhas de contexto mostradas quando um diff unificado for criado. Isso tem precedência sobre qualquer valor da opção "-U" ou "--unified" passado na linha de comando diff do Git.

- `GIT_EXTERNAL_DIFF`

  Quando a variável de ambiente `GIT_EXTERNAL_DIFF` é configurada, o programa informado nele é chamado, em vez do "diff" descrito acima. Para um caminho que é adicionado, removido ou modificado, a variável `GIT_EXTERNAL_DIFF` é chamado com 7 parâmetros:`path old-file old-hex old-mode new-file new-hex new-mode`onde:

- <old|new>-file

  são os arquivos que `GIT_EXTERNAL_DIFF` pode utilizar para ler o conteúdo do <antigo|novo>,

- <old|new>-hex

  são os hashes SHA-1 com 40 hexadecimais,

- <old|new>-mode

  são a representação octais dos modos dos arquivos.Os parâmetros do arquivo podem apontar para o arquivo de trabalho do usuário (`new-file` em "git-diff-files" por exemplo), `/dev/null` (`old-file` quando um novo arquivo for adicionado por exemplo) ou um arquivo temporário (um `arquivo antigo` no índice por exemplo). A variável `GIT_EXTERNAL_DIFF` não deve se preocupar com o desvinculamento do arquivo temporário --- ele é removido quando a variável `GIT_EXTERNAL_DIFF` termina.Para um caminho que não foi mesclado, `GIT_EXTERNAL_DIFF` é chamado com 1 parâmetro, <caminho>.Para cada caminho `GIT_EXTERNAL_DIFF` que é chamado, duas variáveis de ambiente,`GIT_DIFF_PATH_COUNTER` e `GIT_DIFF_PATH_TOTAL` são definidas.

- `GIT_DIFF_PATH_COUNTER`

  Um contador com base 1 incrementado por um em cada caminho.

- `GIT_DIFF_PATH_TOTAL`

  A quantidade total dos caminhos.

### Outros

- `GIT_MERGE_VERBOSITY`

  Um número que controla a quantidade de saída demonstrada pela estratégia de mesclagem recursiva. Substitui o `merge.verbosity`. Consulte [git-merge[1\]](https://git-scm.com/docs/git-merge/pt_BR)

- `GIT_PAGER`

  Essa variável de ambiente substitui o `$PAGER`. Caso esteja definido como uma string vazia ou com o valor "cat", o Git não iniciará um pager. Consulte também a opção `core.askPass` no [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR).

- `GIT_PROGRESS_DELAY`

  Um número que controla quantos segundos atrasar antes de mostrar os indicadores opcionais do progresso. A predefinição retorna para `2`.

- `GIT_EDITOR`

  Essa variável de ambiente substitui o `$EDITOR` e o `$VISUAL`. É usado por vários comandos Git quando, no modo interativo, um editor deve ser iniciado. Consulte também [git-var[1\]](https://git-scm.com/docs/git-var/pt_BR) e a opção `core.editor` no [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR).

- `GIT_SSH`

- `GIT_SSH_COMMAND`

  Caso alguma destas variáveis de ambiente esteja definida, o comando *git fetch* e o *git push* utilizarão o comando informado em vez do *ssh* quando precisarem se conectar com um sistema remoto. Os parâmetros da linha de comando passados para o comando configurado, são determinados pela variante *ssh*. Para mais detalhesm consulte a opção de configuração `ssh.variant` no [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR).A variável `$GIT_SSH_COMMAND` tem precedência sobre a variável `$GIT_SSH` que é interpretado pelo shell, permite que argumentos adicionais sejam incluídos. A variável `$GIT_SSH`, por outro lado, deve ser apenas o caminho para um programa (que pode ser um script shell do wrapper, caso as opções adicionais sejam necessárias).Geralmente é mais fácil configurar as opções desejadas através do seu arquivo pessoal `.ssh/config`. Consulte a documentação do ssh para obter mais detalhes.

- `GIT_SSH_VARIANT`

  Se esta variável de ambiente estiver configurada, ela substitui a detecção automática do Git, caso `GIT_SSH`/`GIT_SSH_COMMAND`/`core.sshCommand` se refere ao OpenSSH, plink ou tortoiseplink. Esta variável substitui a configuração `ssh.variant` que serve ao mesmo propósito.

- `GIT_ASKPASS`

  Caso esta variável do ambiente esteja definida, os comandos Git que precisam obter as senhas ou as frases secretas (para a autenticação HTTP ou IMAP por exemplo) chamarão esse programa com um prompt adequado como argumento da linha de comando e irão ler a senha em seu STDOUT. Consulte também a opção `core.askPass` no [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR).

- `GIT_TERMINAL_PROMPT`

  Caso esta variável de ambiente esteja definida como `0`, o git não será solicitado no terminal (ao solicitar uma autenticação HTTP por exemplo).

- `GIT_CONFIG_NOSYSTEM`

  Independente se você ignore as configurações de leitura do arquivo `$(prefix)/etc/gitconfig` do sistema. Essa variável de ambiente pode ser usada junto com `$HOME` e o `$XDG_CONFIG_HOME` para criar um ambiente previsível para um script exigente, ou você pode configurá-la temporariamente para evitar o uso de um arquivo `/etc/gitconfig` com problemas, enquanto aguarda alguém com permissões suficientes para corrigi-lo.

- `GIT_FLUSH`

  Caso esta variável de ambiente estiver definida como "1", então os comandos como *git blame* (no modo incremental), *git rev-list*, *git log*, *git check-attr* e *git check-ignore* serão impor uma descarga do fluxo gerado depois que cada registro tenham sido esvaziado. Se essa variável for definida como *0*, a saída destes comandos será feita utilizando toda a E/S na memória intermédia (buffer). Se essa variável de ambiente não seja definida, o Git escolherá a descarga em uma memória intermédia ou orientada no esvaziamento dos registros, para ver se o stdout parece ter sido redirecionado para um arquivo ou não.

- `GIT_TRACE`

  Ativa o rastreio geral das mensagens, como por exemplo expansão do pseudônimo, execução interna dos comandos e a execução externa dos comandos.Caso esta variável esteja definida como `1`, `2` ou `true` (a comparação não diferencia as maiúsculas das minúsculas), as mensagens de rastreio serão impressas no stderr.Caso a variável seja configurada com um valor inteiro maior que 2 e menor que 10 (estritamente), o Git interpretará este valor como um descritor de arquivo aberto e tentará gravar as mensagens de monitoramento neste descritor do arquivo.Como alternativa, caso a variável estiver definida como um caminho absoluto (começando com um caractere */*), o Git interpretará isso como um caminho do arquivo e tentará anexar as mensagens de rastreio nelas.Desativar a variável ou defini-la como vazia *0* ou *false* (não faz distinção entre maiúsculas e minúsculas) desativa as mensagens de monitoramento.

- `GIT_TRACE_FSMONITOR`

  Ativa as mensagens de rastreamento para a extensão do monitor do sistema de arquivos. Consulte `GIT_TRACE` para conhecer opções de saída de rastreio disponíveis.

- `GIT_TRACE_PACK_ACCESS`

  Permite rastrear as mensagens para todos os acessos para qualquer pacote. Para cada acesso, é registrado o nome do arquivo do pacote e um *offset*. Pode ser útil para solucionar alguns problemas de desempenho relacionados ao pacote. Consulte `GIT_TRACE` para conhecer opções de saída de rastreio disponíveis.

- `GIT_TRACE_PACKET`

  Ativa o rastreio das mensagens para todos os pacotes que entram ou saem de um determinado programa. Isso pode ajudar na depuração da negociação dos objetos ou de outros problemas de protocolo. O rastreamento é desativado em um pacote que comece com "PACK" (porém consulte `GIT_TRACE_PACKFILE` abaixo). Consulte `GIT_TRACE` para conhecer opções de saída de rastreio disponíveis.

- `GIT_TRACE_PACKFILE`

  Permite o monitoramento dos arquivos dos pacotes enviados ou recebidos através de um determinado programa. Diferente de outras saídas monitoradas, esse monitoramento é literalmente: sem cabeçalhos e sem a citação dos dados binários. Você quase que certamente vai querer direcionar para um arquivo (`GIT_TRACE_PACKFILE=/tmp/my.pack` por exemplo) em vez de exibi-lo no terminal ou misturá-lo com uma outra saída monitorada.Observe que atualmente isso é implementado apenas para o lado do cliente dos clones e das buscas.

- `GIT_TRACE_PERFORMANCE`

  Ativa as mensagens de rastreamento relacionadas ao desempenho, como por exemplo, o tempo total da execução de cada comando Git. Consulte `GIT_TRACE` para conhecer opções de saída de rastreio disponíveis.

- `GIT_TRACE_SETUP`

  Permite que as mensagens de rastreamento imprimam o .git, a árvore de trabalho e o diretório de trabalho atual após o Git concluir a sua fase de configuração. Consulte `GIT_TRACE` para conhecer opções de saída de rastreio disponíveis.

- `GIT_TRACE_SHALLOW`

  Ativa o rastreio das mensagens que podem ajudar na depuração da busca/clonagem dos repositórios rasos. Consulte `GIT_TRACE` para conhecer opções de saída de rastreio disponíveis.

- `GIT_TRACE_CURL`

  Permite um rastreamento curl completo de todos os dados que foram recebidos e enviados, incluindo as informações descritivas, do protocolo de transporte git. É semelhante a fazer curl `--trace-ascii` na linha de comando. Consulte `GIT_TRACE` para conhecer as opções disponíveis geradas pelo rastreio.

- `GIT_TRACE_CURL_NO_DATA`

  Quando um rastreamento curl está ativado (consulte `GIT_TRACE_CURL` acima), não despeje os dados (ou seja, apenas despeje as linhas de informações e os cabeçalhos).

- `GIT_TRACE2`

  Permite mensagens de rastreamento com mais detalhes través da biblioteca "trace2". A saída do `GIT_TRACE2` é um formato simples de texto para facilitar a leitura das pessoas.Caso esta variável esteja definida como `1`, `2` ou `true` (a comparação não diferencia as maiúsculas das minúsculas), as mensagens de rastreio serão impressas no stderr.Caso a variável seja configurada com um valor inteiro maior que 2 e menor que 10 (estritamente), o Git interpretará este valor como um descritor de arquivo aberto e tentará gravar as mensagens de monitoramento neste descritor do arquivo.Alternativamente, caso a variável esteja definida como um caminho absoluto (começando com um caractere */*), Git interpretará isso como um caminho de arquivo e tentará anexar as mensagens de rastreamento a ela. Caso o caminho já exista e for um diretório, as mensagens de rastreamento serão gravadas em arquivos (uma por processo) nesse diretório, nomeada de acordo com o último componente do SID e um contador opcional (para evitar colisões de nome de arquivo).Além disso, caso a variável esteja definida como `af_unix:[<socket_type>:]<caminho-absoluto>`, o Git tentará abrir o caminho como um soquete de domínio Unix. O tipo de soquete pode ser `stream` ou `dgram`.Desativar a variável ou defini-la como vazia *0* ou *false* (não faz distinção entre maiúsculas e minúsculas) desativa as mensagens de monitoramento.Para mais detalhes, consulte [Trace2 documentation](https://git-scm.com/docs/api-trace2/pt_BR).

- `GIT_TRACE2_EVENT`

  Esta configuração registra um formato com base no JSON que é adequado para a interpretação da máquina. Consulte `GIT_TRACE2` para conhecer as opções disponíveis para o monitoramento e o link:technical/api-trace2.html [documentação do Trace2] para obter todos os detalhes.

- `GIT_TRACE2_PERF`

  Além das mensagens texto disponíveis em `GIT_TRACE2`, esta configuração escreve o formato da base da coluna para compreender as regiões aninhadas. Consulte `GIT_TRACE2` para conhecer as opções disponíveis para o monitoramento e o link:technical/api-trace2.html [documentação do Trace2] para obter todos os detalhes.

- `GIT_TRACE_REDACT`

  É predefinido que quando o monitoramento seja ativado, o Git redita os valores dos cookies, o cabeçalho "Autorização:" e o cabeçalho "Autorização do proxy:". Defina esta variável como `0` para evitar esta redação.

- `GIT_LITERAL_PATHSPECS`

  Definir essa variável como `1` fará com que o Git trate todos os pathspecs de forma literal, e não como padrões glob. Como, por exemplo, a execução do `GIT_LITERAL_PATHSPECS=1 git log -- '*.c'` procurará pelos commits que tocam no caminho `*.c` e não nos caminhos que coincidem com o agrupamento `*.c`. Você pode querer isso caso esteja alimentando caminhos literais para o Git (como, por exemplo, os caminhos informados anteriormente a você pelo `git ls-tree`, `--raw`, saída do diff, etc).

- `GIT_GLOB_PATHSPECS`

  Definir essa variável como `1` fará com que o Git trate todos os pathspecs como padrões "glob" (também informados como "glob" mágico).

- `GIT_NOGLOB_PATHSPECS`

  Definir essa variável como `1` fará com que o Git trate todos os pathspecs como literal (também informados como mágica "literal").

- `GIT_ICASE_PATHSPECS`

  Definir essa variável como `1` fará com que o Git trate todos os pathspecs como indiferente para maiúsculas e minúsculas.

- `GIT_REFLOG_ACTION`

  Quando uma "ref" é atualizada, são criadas as entradas do reflog para acompanhar a razão da "ref" ter sido atualizada (que geralmente é o nome do comando de alto nível que atualizou a "ref"), além dos valores antigos e novos da "ref". Um comando Porcelana com script pode usar a função auxiliar *set_reflog_action* no comando `git sh setup` para definir o seu nome para essa variável quando é invocado como o comando de alto nível pelo usuário final, que será registrado no corpo do reflog.

- `GIT_REF_PARANOIA`

  Caso seja definido como `1`, inclua as referências quebradas ou com nomes incorretos ao se iterar sobre as listas das referências. Em um repositório normal, não corrompido, isso não faz nada. No entanto, habilitá-lo pode ajudar o git a detectar e abortar algumas operações na presença de referências quebradas. O Git define essa variável de forma automática durante a execução das operações destrutivas como [git-prune[1\]](https://git-scm.com/docs/git-prune/pt_BR). Você não precisa configurá-lo sozinho, a menos que queira ser paranóico para garantir que uma operação toque em cada "ref" (caso esteja clonando um repositório para fazer uma cópia de segurança por exemplo).

- `GIT_ALLOW_PROTOCOL`

  Caso seja definido como uma lista de protocolos separados por dois pontos, comporte-se como se a opção de configuração `protocol.allow` esteja definida como `never`, e cada um dos protocolos listados possua `protocol.<nome>.allow` definido como `always` (substituindo qualquer configuração já existente). Em outras palavras, qualquer protocolo não mencionado será proibido (ou seja, esta é uma lista de permissões e não uma lista negra). Consulte a descrição do `protocol.allow` no [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR) para mais detalhes.

- `GIT_PROTOCOL_FROM_USER`

  Defina como `0` para evitar que os protocolos utilizados por `fetch/push/clone` sejam configurados por `user`. É útil para restringir a inicialização recursiva do submódulo de um repositório não confiável ou para programas que alimentam as URLS potencialmente não confiáveis aos comandos git. Para mais detalhes consulte [git-config[1\]](https://git-scm.com/docs/git-config/pt_BR).

- `GIT_PROTOCOL`

  Apenas para utilização interna. Used in handshaking the wire protocol. Contains a colon *:* separated list of keys with optional values *key[=value]*. Presence of unknown keys and values must be ignored.

- `GIT_OPTIONAL_LOCKS`

  Caso seja definido como 0, o Git concluirá qualquer operação solicitada sem executar outra operação opcional onde se exija um bloqueio. Como um efeito colateral isso impedirá que o comando `git status` atualize o índice por exemplo. É útil para os processos que estão em execução no segundo plano que não queiram causar contenção do bloqueio com as outras operações no repositório. A predefinição retorna para `1`.

- `GIT_REDIRECT_STDIN`

- `GIT_REDIRECT_STDOUT`

- `GIT_REDIRECT_STDERR`

  Apenas no Windows: permite redirecionar os identificadores predefinidos de *input/output/error* para os caminhos definidos através das variáveis do ambiente. Em particular isso é útil nos aplicativos "multi-threaded" onde a maneira canônica de encaminhar os identificadores predefinidos através do `CreateProcess()` não seja uma opção pois exigiria que os identificadores fossem marcados como herdáveis (e consequentemente **todo** processo gerado os herdaria, possivelmente fazendo o bloqueio das operações do Git). A intenção primária de utilização é utilizar os pipes informados para comunicação (`\\.\pipe\my-git-stdin-123` por exemplo).Dois valores especiais são compatíveis: `off` simplesmente fechará o identificador predefinido correspondente e caso `GIT_REDIRECT_STDERR` seja `2> & 1`, a predefinição do erro será redirecionado para o mesmo identificador na saída padrão.

- `GIT_PRINT_SHA1_ELLIPSIS` (descontinuado)

  Caso seja definido como `yes`, imprima uma elipse seguido de um valor (abreviado) SHA-1. Isso afeta as indicações dos HEADs desanexados ([git-checkout[1\]](https://git-scm.com/docs/git-checkout/pt_BR)) e a saída diff bruta ([git-diff[1\]](https://git-scm.com/docs/git-diff/pt_BR)). A impressão de uma elipse nos casos mencionados não é mais considerada adequada e é provável que a compatibilidade seja removida em um futuro próximo (junto com a variável).

## Discussão

Mais detalhes estão disponíveis no [capítulo dos conceitos do Git no manual do usuário](https://git-scm.com/docs/user-manual/pt_BR#git-concepts) e [gitcore-tutorial[7\]](https://git-scm.com/docs/gitcore-tutorial/pt_BR).

Um projeto Git normalmente consiste em um diretório de trabalho com um subdiretório ".git" no ponto mais alto. O diretório .git contém, entre outras coisas, um banco de dados dos objetos compactados representando o histórico completo do projeto, um arquivo para o "índice" que vincula este histórico ao conteúdo atual da árvore de trabalho e informa os ponteiros para este histórico, como as tags e os cabeçalhos do ramo.

O banco de dados do objeto contém os objetos dos tipos da árvore principal: bolhas, que contêm os dados do arquivo; árvores, que apontam para as bolhas e as outras árvores para criar as hierarquias do diretório; e os commits, cada qual faz referência a uma única árvore e algum número do commit do pai.

O commit, equivalente ao que os outros sistemas chamam do "conjunto de alterações" ou "versão", representa uma etapa no histórico do projeto e cada pai representa uma etapa anterior. Os commits com mais de um pai representam as mesclagens das linhas independentes do desenvolvimento.

Todos os objetos são nomeados pelo hash SHA-1 do seu conteúdo, normalmente gravados como uma sequência com 40 dígitos hexadecimais. Tais nomes são globalmente únicos. Todo o histórico que antecede a um commit pode ser comprovado assinando apenas este commit. Um quarto tipo de objeto, a tag, é fornecida para esta finalidade.

Quando criados pela primeira vez, os objetos são armazenados em arquivos individuais, porém, visando uma maior eficiência, podem ser compactados posteriormente em "pacotes de arquivos".

Os Ponteiros informados chamados refs marcam os pontos interessantes na história. Uma "ref" pode conter o nome SHA-1 de um objeto ou o nome de outra referência. As referências com nomes que comecem com `ref/head/` contêm o nome SHA-1 do commit (ou "head") mais recente de um ramo em desenvolvimento. Os nomes SHA-1 das tags de interesse são armazenados em `ref/tags/`. Uma referência especial chamada `HEAD` contém o nome da ramificação com a averiguação do momento.

O arquivo do índice é inicializado com uma lista de todos os caminhos e para cada caminho, um objeto bolha e um conjunto de atributos. O objeto bolha representa o conteúdo do arquivo no cabeçalho do ramo atual. Os atributos (hora da última alteração, tamanho, etc.) são obtidos do arquivo correspondente na árvore de trabalho. As alterações subsequentes na árvore de trabalho podem ser encontradas comparando estes atributos. O índice pode ser atualizado com um novo conteúdo e os novos commits podem ser criadas a partir do conteúdo armazenado no índice.

O índice também é capaz de armazenar as várias entradas (chamadas de "estágios") para um determinado nome do caminho. Esses estágios são utilizados para manter as várias versões não mescladas de um arquivo quando uma mesclagem está em andamento.

## DOCUMENTAÇÃO ADICIONAL

Consulte as referências na seção "descrição" para começar a utilizar o Git. O seguinte tem provavelmente bem mais detalhes do que o necessário para um usuário iniciante.

O [capítulo de conceitos do Git do manual do usuário](https://git-scm.com/docs/user-manual/pt_BR#git-concepts) e o [gitcore-tutorial[7\]](https://git-scm.com/docs/gitcore-tutorial/pt_BR) fornecem introduções à arquitetura subjacente do Git.

Para obter uma visão geral das recomendações do fluxo de trabalho, consulte [gitworkflows[7\]](https://git-scm.com/docs/gitworkflows/pt_BR).

Para mais alguns exemplos úteis, consulte também o documento [howto](https://git-scm.com/docs/howto-index/pt_BR).

As entranhas estão documentadas no [Documentação da API do Git](https://git-scm.com/docs/api-index/pt_BR).

Os usuários que estiverem migrando do CVS também podem querer ler [gitcvs-migration[7\]](https://git-scm.com/docs/gitcvs-migration/pt_BR).