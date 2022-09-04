---
layout: page
title: Category
description: >
  Category docs
hide_description: true
sitemap: false
---

카테고리와 관련한 문서입니다.


1. category table
{:toc}


## Summary

카테고리는 문제들을 집합화하여 관리할 수 있는 기능입니다.
카테고리는 생성하고 관리할 수 있는 권한은 Admin, Super Admin만 가능합니다. 관리 하는 방법은 `계정 관리 -> Management -> 카테고리` 에서 가능합니다.

Admin의 경우 총 3가지 타입의 문제 권한이 주어집니다. 이 권한은 문제를 관리할 수 있는 카테고리 권한도 포함됩니다. **권한 없음**의 경우 일반사용자와 마찬가지로 문제를 생성할 수 있는 권한이 없습니다. **본인 권한**의 경우 문제 생성 및 삭제가 가능하나 그 권한은 본인이 만들고 생성한 문제로 제한됩니다. **모든 권한**의 경우 모든 문제에 대한 권한이 부여됩니다. 이러한 권한 조정은 Super Admin 계정에 의해 사용자 관리영역에서 조정 할 수 있습니다.
{:.note}

## Make a Category
카테고리는 문제들을 집합화 하여 별도의 리스트로 관리하는 것이기 때문에 문제가 사전에 존재해야 합니다.
문제를 생성하는 방법에 대해서는 [Problem 문서](problem.md)를 참고하시기를 바랍니다.

카테고리는 문제를 참조하고 있을뿐 별도의 문제가 생성 혹은 문제에 대한 데이터가 변경되지 않습니다. 그러므로 카테고리를 생성 혹은 삭제를 한다고 하더라도 카테고리 내에 존재하는 문제들은 영향을 미치지 않습니다.


### Category Format
카테고리 생성 자체는 어렵지 않습니다. 아래 설명하는 형식에 맞추어 작성해주시면 됩니다.

#### 제목
제목은 문제들을 집합화한 한 분류를 대표할 수 있는 제목으로 작성해주시면 됩니다. 예로들어 A+B, A-B, A*B, A/B 같은 문제들이 있을 때 사칙연산이라는 타이틀로 문제들을 관리할 수 있을 겁니다.

#### 내용
해당 카테고리의 내용에 대해 설명하는 란입니다.
현재는 사용자에게 직접적으로 보이지는 않지만, 추후에 텍스트가 표시 될 예정입니다.

#### 문제
해당 카테고리에 넣을 문제들을 검색하여 추가할 수 있습니다. 검색은 제목으로만 검색됩니다.

<br /><br /><br />

Continue with [Contest](contest.md){:.heading.flip-title}
{:.read-more}


[mm]: https://guides.github.com/features/mastering-markdown/
[ksyn]: https://kramdown.gettalong.org/syntax.html
[ksyntab]:https://kramdown.gettalong.org/syntax.html#tables
[rtable]: https://dbushell.com/2016/03/04/css-only-responsive-tables/
