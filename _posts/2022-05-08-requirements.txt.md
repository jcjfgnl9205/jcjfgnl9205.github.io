---
title: requirements.txtとは
author:
  name: Park Cheol Hwi
  link: https://github.com/jcjfgnl9205
date: '2022-05-08'
categories: [python, pip, requirements.txt]
tags: [requirements.txt]
pin: true
---

  > requirements.txtとは  
    他の人とプロジェットを共有したり、本番環境に反映させるときに、プロジェクトに必要な外部パッケージを反映させる必要がある。  
  この外部パッケージの名前やバージョンがあるファイルが requirements.txt　です。  
  一言でいうと、対象のプロジェクトにpip installする必要があるパッケージリストを記載しているファイルです。
  {: .prompt-note }  

## requirements.txtの使用方法

1. 自分のプロジェクトにインストるされているパッケージリストを見る  
```console
$ pip freeze
```
![freeze1](/assets/img/20220508/pip-freeze.png){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px; height: 700px;" }  

2. requirements.txtを生成する方法  
```console
$ pip freeze > requirements.txt
```  
下記のようにrequirements.txtファイルが生成され、パッケージの名前とバージョンが入っていることが確認できる。  
![freeze2](/assets/img/20220508/pip-freeze2.png){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" }  

3. 生成したrequirements.txtにあるパッケージリストを環境にインストるする方法
    対象のプロジェクトでターミナルに下記のコマンドを入力する。
```console
$ pip install -r requirements.txt
```  

## 最後に
開発をしている際、パッケージのバージョンが違うだけでエラーが出ることが多いです。  
requirements.txtで管理することで効率的に開発することができると思いました。
