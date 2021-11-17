---
title:  "[Github Blog] 블로그 css 수정"

categories:
  - Github
tags:
  - [Blog, Github]

toc: true
toc_sticky: true
 
date: 2011-11-12
last_modified_at: 2011-11-12
---

### :ok: 글씨 font size   


`_sass/minimal-mistakes/_page.scss`    
 line : 113 수정    

```html   
  p,
  li,
  dl {
    font-size: 0.8em; // 1em;
  }
```

### :left_right_arrow: toc (목차) 위치 수정
`single.html`  
sidebar__right -> <u>sidebar__left</u> 로 수정했다.  
class 에서 float를 바꿔서 되게 하나봄.  
요것만 바꿔도 오른쪽이 넓어져서 전체 사이즈를 원래대로 돌려도 되겠다.

```html
<aside class="sidebar__left {% if page.toc_sticky %}sticky{% endif %}">
```

`_archive.scss & _page.scss`  
2군데 padding-right 주석

```html
    // padding-right: $right-sidebar-width-narrow;
    // padding-right: $right-sidebar-width;
```