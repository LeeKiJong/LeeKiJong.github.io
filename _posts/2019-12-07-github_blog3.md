---
layout: post
title:  "쉽고 빠른 지킬 깃허브 블로그 만드는 법 3"
date:   2019-12-07
author: LeeKiJong
categories: etc
tags: 깃허브 블로그 jekyll 지킬 
---

이번에는 지킬로 깃허브 블로그 만들기 3편입니다.  
댓글창도 만들고 블로그도 꾸몄는데 방문자가 없다면 꾸민 이유가 없겠죠.  
그래서 이번에는 웹서핑을 하는 사람들이 정보를 검색했을 때 우리의 블로그가 검색 결과에 나오게 하는 방법을 소개하겠습니다.

<hr>
<h2>Google</h2>
[https://search.google.com/search-console/about](https://search.google.com/search-console/about)  
우선 Google Search Console로 들어가서 시작하기 버튼을 누르고 로그인을 해주세요.  
그 다음은 파일 3개를 블로그 리포지토리 최상위(/root)에 만들어줘야 합니다.  
아마 테마를 제대로 다운로드 받았다면 제작자분이 sitemap.xml을 만들어 놓으셨을 거예요.  
그래도 혹시 모르니 적어두겠습니다. 그대로 복사해서 만들어주세요.  
  
sitemap.xml  
[https://github.com/LeeKiJong/LeeKiJong.github.io/blob/master/sitemap.xml](여기 코드를 복사해서 쓰세요!)
 
feed.xml  

[여기 코드를 복사해서 쓰세요!](https://github.com/LeeKiJong/LeeKiJong.github.io/blob/master/feed.xml)
 
robots.txt  

[여기 코드를 복사해서 쓰세요!]([https://github.com/LeeKiJong/LeeKiJong.github.io/blob/master/robots.txt)

Sitemap: http://***여기에는 블로그 주소를 써주세요.***/sitemap.xml

 
모두 작성하셨으면 한 번 주소에 '자신 블로그 주소/sitemap.xml' 페이지가 정상적으로 나오는 지 확인해주세요.
정상적으로 나온다면 다시 Google search Console로 가서  
![url](https://user-images.githubusercontent.com/52438368/70368963-4ca29900-18f5-11ea-9dde-bd7a13e19248.PNG)  
저 칸에 블로그 주소를 써주세요.  
그러면 사이트 등록이 될텐데 등록이 되었다면 크롤링 > sitemap 추가로 가서 아까 만든 sitemap.xml과 feed.xml을 등록해주세요.  
제대로 따라오셨다면 정상적으로 등록이 될 것입니다.  
색인이 접수 중이라면 기다려주시면 접수가 완료 될 것입니다.  
이 과정을 한다고 바로 검색 결과에 뜨는 게 아니라 조금 기다리셔야 해요.  
저는 한 3~4일 정도 기다린 거 같아요...  
그래도 네이버보다는 빨리 뜬 거 같아요.  
다음>구글>네이버 순으로 등록이 되더라고요.

<hr>
<h2>Naver</h2>
네이버, 다음은 구글보다 쉬우니까 금방해요.  

[https://searchadvisor.naver.com/](https://searchadvisor.naver.com/)
네이버 서치어드바이저에 들어가셔서 로그인하신 후 웹마스터 도구를 눌러주세요.  
![naver](https://user-images.githubusercontent.com/52438368/70369006-08fc5f00-18f6-11ea-8974-3f4647f9895d.PNG)  
이 화면이 뜬다면 가운데 빈칸에 블로그 주소를 써주세요.  
그러면 이 화면이 나옵니다.  
![naver2](https://user-images.githubusercontent.com/52438368/70369041-9b046780-18f6-11ea-9e35-3f70ab2ac29e.PNG)  
저기 설명에 나온대로 html 파일을 다운로드 하셔서 리포지토리 최상위에 만들어주세요.  
저 주소 그대로 써서 사이트가 제대로 나오는 지 확인도 하시는 게 좋아요.  여러분과 저의 html 정보는 달라요. 제 꺼 쓰시면안돼요!  
그렇게 하셔서 블로그를 등록하셨으면 이제 sitemap.xml과 feed.xml을 등록해야해요.

![naver3](https://user-images.githubusercontent.com/52438368/70369070-10703800-18f7-11ea-9f91-b39e433a4560.PNG)  
저기에 두 파일다 등록해주시고  
몇 일 기다리시면 네이버에도 검색 결과가 나옵니다!!

<hr>
<h2>Daum</h2>
마지막으로 다음입니다.
[https://register.search.daum.net/index.daum](https://register.search.daum.net/index.daum)  
여기 접속하셔서  
![daum](https://user-images.githubusercontent.com/52438368/70369101-8a082600-18f7-11ea-9b8f-102e8da3db59.PNG)  
블로그 등록을 체크하시고 블로그 이름을 써서 확인을 눌러주세요.  
그리고 이메일 주소 등등 다 작성하시면 나머지는 다음이 다 해줍니다. 이게 제일 편해요 ㅎㅎ..  

그럼 여기까지가 검색 결과 나오게 하는 법이였고 다음 포스트는 뭐를 해야할까요..  
블로그의 기본적인 설정은 여기까지였고 나머지는 꾸미기만 하면 될거같아요.  
궁금하신 거 댓글로 적어주시면 제가 따로 조사해서 포스트하겠습니다.



