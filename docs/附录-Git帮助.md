# 附录-Git帮助

```
[root@youyifeng ~]# git help
usage: git [--version] [--help] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p|--paginate|--no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

The most commonly used git commands are:
   add        Add file contents to the index
   bisect     Find by binary search the change that introduced a bug
   branch     List, create, or delete branches
   checkout   Checkout a branch or paths to the working tree
   clone      Clone a repository into a new directory
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   fetch      Download objects and refs from another repository
   grep       Print lines matching a pattern
   init       Create an empty Git repository or reinitialize an existing one
   log        Show commit logs
   merge      Join two or more development histories together
   mv         Move or rename a file, a directory, or a symlink
   pull       Fetch from and merge with another repository or a local branch
   push       Update remote refs along with associated objects
   rebase     Forward-port local commits to the updated upstream head
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index
   show       Show various types of objects
   status     Show the working tree status
   tag        Create, list, delete or verify a tag object signed with GPG

'git help -a' and 'git help -g' lists available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.

```

显示所有子命令

```
[root@youyifeng ~]# git help -a
usage: git [--version] [--help] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p|--paginate|--no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

available git commands in '/usr/libexec/git-core'

  add                       describe                  lost-found                pull                      show
  add--interactive          diff                      ls-files                  push                      show-branch
  am                        diff-files                ls-remote                 quiltimport               show-index
  annotate                  diff-index                ls-tree                   read-tree                 show-ref
  apply                     diff-tree                 mailinfo                  rebase                    stage
  archive                   difftool                  mailsplit                 receive-pack              stash
  bisect                    difftool--helper          merge                     reflog                    status
  bisect--helper            fast-export               merge-base                relink                    stripspace
  blame                     fast-import               merge-file                remote                    submodule
  branch                    fetch                     merge-index               remote-ext                submodule--helper
  bundle                    fetch-pack                merge-octopus             remote-fd                 subtree
  cat-file                  filter-branch             merge-one-file            remote-ftp                symbolic-ref
  check-attr                fmt-merge-msg             merge-ours                remote-ftps               tag
  check-ignore              for-each-ref              merge-recursive           remote-http               tar-tree
  check-ref-format          format-patch              merge-resolve             remote-https              unpack-file
  checkout                  fsck                      merge-subtree             remote-testpy             unpack-objects
  checkout-index            fsck-objects              merge-tree                repack                    update-index
  cherry                    gc                        mergetool                 replace                   update-ref
  cherry-pick               get-tar-commit-id         mktag                     repo-config               update-server-info
  clean                     grep                      mktree                    request-pull              upload-archive
  clone                     hash-object               mv                        rerere                    upload-pack
  column                    help                      name-rev                  reset                     var
  commit                    http-backend              notes                     rev-list                  verify-pack
  commit-tree               http-fetch                pack-objects              rev-parse                 verify-tag
  config                    http-push                 pack-redundant            revert                    web--browse
  count-objects             imap-send                 pack-refs                 rm                        whatchanged
  credential                index-pack                patch-id                  send-pack                 write-tree
  credential-cache          init                      peek-remote               sh-i18n--envsubst
  credential-cache--daemon  init-db                   prune                     shell
  credential-store          log                       prune-packed              shortlog

'git help -a' and 'git help -g' lists available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
```
