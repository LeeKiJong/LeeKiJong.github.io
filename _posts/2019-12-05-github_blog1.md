---
layout: post
title:  "쉽고 빠른 지킬 깃허브 블로그 만드는 법 1"
date:   2019-12-05
author: LeeKiJOng
categories: etc
tags: 깃허브 블로그 jekyll 지킬 
---

오늘은 깃허브 블로그 만드는 법을 포스트하겠습니다.  
아직 블로그를 만든 지는 별로 안됐지만 나름 뿌듯함, 그리고 포스트한 내용은 확실히 공부했다는 자신감이 생겼다는 것을 느끼고 다른 개발자 분들도 한 번 쯤은 만들어 보셨으면 해서 이렇게 글을 올립니다.  
제가 만들 방식은 jekyll(지킬)을 이용한 깃허브 블로그입니다.  
제가 직접 블로그 만든 방식을 올렸으니 동작이 안되는 부분이 있거나 궁금하신 게 있다면 댓글을 남겨주세요.  

<hr>

<h2>지킬 테마 찾기</h2>
우선 마음에 드는 지킬 테마를 찾아야겠죠.  
링크는 여기! [http://jekyllthemes.org/](http://jekyllthemes.org/)  
![지킬](https://user-images.githubusercontent.com/52438368/70197812-58a12600-1750-11ea-8903-b7f02e7e0c3b.PNG)  

깔끔하고 심플한 테마 많으니 천천히 골라보세요.  
저는 'centrarium' 이라는 테마를 사용했습니다. 'clean blog' 도 추천해요. 아마 'centrarium' 이 없었다면 저 테마로 했을수도..  
그리고 License도 잘 읽어 보시길 바랍니다. 찾아보기 힘들다면 그냥 MIT License로 하시는 게 제일 마음이 편해요.. ㅎㅎ..  
마음에 드는 테마를 찾았으면 그 테마를 누르고 Homepage 버튼을 눌러주세요.  

![homepage](https://user-images.githubusercontent.com/52438368/70198579-94d58600-1752-11ea-934a-a706eaf00f8b.PNG)  
그러면 다음 화면이 나오는데 이 화면에서 fork를 누르고 조금만 기다리면 자동으로 내 리포지토리에 테마를 그대로 복사한 파일이 생깁니다.  
테마를 다운받는 방식에는 fork와 clone이 있는 데 저는 fork를 사용했습니다.
![fork](https://user-images.githubusercontent.com/52438368/70198584-969f4980-1752-11ea-8f1f-effe7789cf14.PNG)  
그러면 일단 테마를 찾은 후 다운로드는 끝입니다.

<hr>

<h2>블로그 설정하기</h2>
리포지토리가 생성되면 Setting을 눌러주세요,  
![name](https://user-images.githubusercontent.com/52438368/70198782-2d6c0600-1753-11ea-89b5-dcf934deb80f.PNG)  
그 후엔 이름은 자기 깃허브 이름을 넣고 github.io를 붙여주세요.  
예를 들어 제 블로그 같은 경우에는  
LeeKiJong.github.io  
가 되겠죠. 이름을 쓰셨으면 Rename을 눌러주세요.  
리포지토리 이름이 변경되었으면 다시 파일 목록으로 돌아가주세요.  
![config](https://user-images.githubusercontent.com/52438368/70198977-d155b180-1753-11ea-866a-9c16a679c4f9.PNG)  
그 후 config.yml 파일을 눌러서 들어간 후



