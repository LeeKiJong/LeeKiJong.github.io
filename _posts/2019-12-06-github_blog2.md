---
layout: post
title:  "쉽고 빠른 지킬 깃허브 블로그 만드는 법 2"
date:   2019-12-06
author: LeeKiJong
categories: etc
tags: 깃허브 블로그 jekyll 지킬 
---

오늘은 지킬로 깃허브 블로그 만들기 2편입니다.  
이번에는 discuss를 이용한 댓글 만들기를 하겠습니다. 천천히 잘 따라와보세요. 별로 어렵지 않습니다.  
우선 아래 사이트에 접속하셔서 회원가입 후 로그인해주세요.
[https://disqus.com/](https://disqus.com/)  
회원가입이 끝나면 Get Started를 클릭해주세요.  
![get](https://user-images.githubusercontent.com/52438368/70294901-75a92800-1828-11ea-80ef-f92240c2abf3.PNG)  

그 다음에는 아래에 있는 'I want to install...' 버튼을 누르시고,  
![pick](https://user-images.githubusercontent.com/52438368/70294905-780b8200-1828-11ea-8dad-908c23869387.PNG)  

WebSite name에는 그냥 깃허브 닉네임 쓰셔도 되고 딴거 쓰셔도 돼요.  
![create](https://user-images.githubusercontent.com/52438368/70294909-7a6ddc00-1828-11ea-94a7-f16a3699dcd1.PNG)  

그리고, 저희는 무료로 사용하는 걸 원하기 때문에 Basic칸 안에 있는 버튼을 눌러주세요.  
![basic](https://user-images.githubusercontent.com/52438368/70294910-7b067280-1828-11ea-97fe-68a14d409feb.png)  

저희는 지킬을 사용했기 때문에 지킬을 눌러주시고,  
![pick2](https://user-images.githubusercontent.com/52438368/70294911-7b067280-1828-11ea-955d-6a7d98d964d2.PNG)  

Post.html에 아래 1번과 같이 생긴 코드를 복사하여 맨 위에 붙여주세요.  
![comments](https://user-images.githubusercontent.com/52438368/70294914-7b9f0900-1828-11ea-9e11-79e99f5f19d2.PNG)  

그 다음엔 2번을 누르면 아래와 같은 코드가 있을 텐데 그 코드도 그대로 복사해서 Post.html에 붙여넣어주세요.  
![comments2](https://user-images.githubusercontent.com/52438368/70294915-7b9f0900-1828-11ea-8ff3-c8ab3fc126ab.PNG)  

다시 Config.yml로 가시면 disqus_shortname: .... 이런 식으로 써져있는 코드가 있을거에요. 여기에 아까 discuss에서  
입력했던 Website name을 적어주시면 됩니다.  
  
<fieldset>

       {% if site.disqus-shortname %}{% include disqus.html %}{% endif %} 

</fieldset> 
이 코드도 Post.html에 넣어주시면됩니다. 그러면 끝이에요.  
여기까지 하면 Post.html 레이아웃을 사용한 게시글 아래 부분에 댓글 창이 생길거에요.  
다음 포스트는 구글, 네이버, 다음에 검색되게 하는 방법을 소개드리겠습니다.







