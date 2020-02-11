---
layout: post
title:  "MVC 패턴을 적용한 Spring 게시판"
date:   2020-02-11
author: LeeKiJong
categories: spring
comments : true
tags: JAVA Spring Framework
cover:  "/assets/java.jpg"
---
<h2>프로젝트 전체 설계</h2>
![10](https://user-images.githubusercontent.com/52438368/74210779-7d75c480-4cd0-11ea-929a-595bbb09a922.PNG)
<h2>DataBase 구축</h2>
```sql
create table mvc_board(
    bId NUMBER(4) PRIMARY KEY,
    bName VARCHAR2(20),
    bTitle VARCHAR2(100),
    bContent VARCHAR(300),
    bDate DATE DEFAULT SYSDATE,
    bHit NUMBER(4) DEFAULT 0,
    bGroup NUMBER(4),
    bStep NUMBER(4),
    bIndent NUMBER(4)
);
commit;
```
