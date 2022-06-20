### git 命令

- 合并分支

  ```shell
  $ git merge xxx  --no-ff
  ```

- 创建dev分支，切换到dev分支

  ```shell
  $ git checkout -b dev
  相当于以下两条命令
  $ git branch dev
  $ git checkout dev
  ```


- 远程提交

  ```shell
  git push origin master
  ```

   向远程origin主机提交本地master分支的代码，确保本地和远程都有master分支。如果master分支不存在，那会新建一个master分支。