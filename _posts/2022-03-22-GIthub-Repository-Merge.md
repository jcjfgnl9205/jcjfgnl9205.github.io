---
title: GithubのRepositoryを合体する
author:
  name: Park Cheol Hwi
  link: https://github.com/jcjfgnl9205
date: '2022-03-22'
categories: [Gitshub, Git]
tags: [Git, Github, repository]
pin: true
---

## GitHub repositoryを合体する  
色んな小さなプロジェクトのRepositoryがどんどん増えていて、複数のRepositoryを一つにまとめたいと思いました。  
新しいRepositoryを作成し、作成したファイルをCommitする方法でもできますが、  
今まで作成したCommit履歴を残したかったので合体する方法を紹介します。  

今回 `project1-frontend Repository`、`project1-backend Repository`のを`NewProject Repository`へ移動します。  
![github01](/assets/img/20220322/github01.png){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" }  



1. 新しい（移動したい）Repositoryを生成する（`NewProject Repository`）
![github02](/assets/img/20220322/github02.png){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" }  


2. 生成したRepositoryをlocalにcloneする  
```console
$ git clone [Repository] 
$ git clone https://github.com/jcjfgnl9205/NewProject.git
```  

3. どんな内容でもコミットする  
README.mdファイルを作成し、下記のコマンドでCommitする  
Commitしないと、subtreeする時エラーになりました。。
```console
$ git add .
$ git commit -m "first commit" 
$ git push origin main 
```
RepositoryにREADME.mdが生成される  
![github03](/assets/img/20220322/github03.png){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" }  

4. Repositoryを合体する  
- `project1-backend Repository`を移動する
```console
$ git subtree add --prefix=[生成するディレクトリ名] [移動したいRepository] [Branch名] 
-
$ git subtree add --prefix=backend https://github.com/jcjfgnl9205/project1-backend.git main 
$ git push origin main 
```
`project1-backend Repository`のファイルがbackendフォルダの中にcommitされるし、  
commit履歴が残ることが確認できます。  
![github04](/assets/img/20220322/github04.png){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" } 
- `project1-frontend Repository`を移動する
```console
$ git subtree add --prefix=[生成するディレクトリ名] [移動したいRepository] [Branch名] 
-
$ git subtree add --prefix=frontend https://github.com/jcjfgnl9205/project1--frontend.git main 
$ git push origin main 
```
`project1-frontend Repository`のファイルがfrontendフォルダの中にcommitされるし、  
commit履歴が残ることが確認できます。  
![github05](/assets/img/20220322/github05.png){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" }  


※合体後、既存の`project1-backend Repository`と`project1-frontend Repository`のrepositoryは削除してもcommit履歴は残る

<br>

以上
