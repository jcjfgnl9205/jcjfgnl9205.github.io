---
title: Web Storageとは？
author:
  name: Park Cheol Hwi
  link: https://github.com/jcjfgnl9205
date: '2022-02-20'
categories: [WebStorage, Cookie]
tags: [Session Storage, Local Storage, Cookie]
pin: true
---

## Web Storage

Web Storageとは、HTML5より使える機能として、データをサーバーではなくクライアントウェブブラウザに保存できる機能として、Cookieと似ている？  

Web Storageは key, valueでデータを保存して、key値でデータが取得できる。  

Local Strogae(永久的に保存する)とSession Storage(一時的に保存する)がそれぞれあるので環境によって使用する。  

Web Storageは、Cookieと同様でサイトのドメインの中でしか使用できない。  

### Web Storage VS Cookie

CookieとWeb Storageは全てブラウザにデータを保存しますが、Cookieのディメリットの部分を保安できる

- Cookieはいつもサーバーにデータを送信する  
  ウェブサイトでCookieを設定すると、全てのRequestはCookie情報を含めてサーバーに送信する  
  Web Storageはデータが保存されるだけで送信されないのでネットワークのトラフィックを軽減することができる  

- Web Storageにもっと多いデータを保存することができる  
  1つのサイトに保存できるCookieは最大20個、容量は4KBが、Web Storageは5MBまで保存することができる  

- オブジェクト情報も保存できる  
  Web Storageには、String型以外にもオプジェットも保存することができるので開発するときにも便利だと思う  

- Web Storageは永久的に保存することができる  
  Cookieの場合、満了日があるのでいつかは削除される。満了日を設定しないとSessionCookieになる。  
  もし、永久的に使いたいCookieがあると満了日を長く設定して解決する方法もあります。(Persistent Cookie)  
  しかし、Web Storageは満了日がないため、保存したデータを永久的に保存することができる  

  > ※Session Cookieとは？  
  サーバーに対するSessionが終了した時点で（通常、ブラウザを終了した時点で）破棄される
  {: .prompt-note }

  > ※Persistent Cookieとは？  
  各Cookieに指定された期間の間、または装置においてCookieを手動で削除するまで装置に残っている
  {: .prompt-note }


### Web Storageの種類

- Local Storage  
    - window.localStorageオブジェクト

    - ブラウザーを閉じても保存されるデータ、明示的に削除されない限り永久的に保存される

    - ドメイン別に生成され、他のドメインのLocal Storageにはアクセスできない

    - 異なるブラウザタブでも同一ドメインであれば同一のLocal Storageを使用する

    - 持続的に必要な情報を保存する場合良い(ex. 自動ログインなど)


- Session Storage
    - window.sessionStorageオブジェクト

    - ページセッションは、ブラウザが開いている限りリフレッシュとページの復旧を経ても残っている

    - ページを新しいタブやウィンドウで開くと, Session Cookieの動作とは異なり、最上位のブラウジング文脈の値を持つ新しいSessionを生成する

    - 同じURLを多数のタブ/ウィンドウで開くと、それぞれのタブ/ウィンドウに対して新しいSession Storageが生成される

    - タブ/ウィンドウを閉じると、Sessionが終わり、Session Storageの中のオブジェクトを初期化する

    - 異なるSession Storageは、互いに影響を与えず、独立的に動作する

    - しばらく必要な情報を保存するのに良い. (ex. 入力したォームの保存、ログインなど)

### 参考

[**LocalStorage**](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)  
[**SessionStorage**](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)

<br>

以上
