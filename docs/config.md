---
layout: page
title: System Config
description: >
  System Config documentation
hide_description: true
sitemap: false
---

시스템 설정과 관련한 문서입니다.

0. this unordered seed list will be replaced by toc as unordered list
{:toc}

## Summary
시스템 설정은 Super Admin(최고 관리자)만 접근이 가능합니다.
기본적으로 SMTP와 Footer에 표시 될 내용들을 설정 할 수 있습니다.

## SMTP
간이 우편 전송 프로토콜을 지원합니다. 일반 사용자들이 정상적으로 이용하기 위해 이메일 인증을 요구하게 되는데, 이 때 시스템에서는 SMTP를 반드시 설정해야 합니다.

### Server
전송 계정의 SMTP Server를 입력하시면 됩니다. 예로들어 GMail일 경우 smtp.gmail.com이 됩니다.

### Port
SMTP 전송 포트를 지정합니다. SMTP는 25/tcp와 587/tcp 포트를 사용하므로, 해당 이메일 서비스에서 각 포트에 맞게 포트를 작성해주시면 됩니다.

해당 이메일 전송 기능은 SSL인증을 활용하지 않으므로 SMTPS는 지원하지 않습니다. 즉, TLS를 써야 하며 추후 SSL 지원을 확대할 경우 TLS-SSL 옵션을 활성화 할 예정입니다.
{.:note}

### Password
해당 이메일 계정의 비밀번호입니다. 간혹 일부 이메일 SMTP 서비스에서는 계정 비밀번호가 아닌, 별도로 주어지는 비밀번호일 수 있습니다.

## Web 설정
기본적인 웹에 대한 설정을 할 수 있습니다.

### 기본 URL
현재 서비스하는 URL 주소를 적어주셔야 합니다. 이는 채점 서버가 찾아가기 위해서 올바르게 작성해야합니다.

### Name
서비스의 대표 이름을 바꿀 수 있습니다.

### Shortcut
서비스 이름의 줄임말을 설정 할 수 있습니다.

### Footer
Footer에 표시할 내용을 작성 할 수 있습니다.

### 사용자 가입 활성화
현재 서비스에 일반 사용자들이 가입을 할 수 있도록 하거나, 이를 비활성화 할 수 있습니다.

### SubmissionList Show All
현재는 별도의 기능은 없으나, 추후 사용자들이 제출한 코드들의 접근 권한을 조정할 때 쓰일 예정입니다.




[config]: https://github.com/hydecorp/hydejack-starter-kit/blob/v9/_config.yml
[social]: https://github.com/hydecorp/hydejack-starter-kit/blob/v9/_data/social.yml
[authors]: https://github.com/hydecorp/hydejack-starter-kit/blob/v9/_data/authors.yml
[strings]: https://github.com/hydecorp/hydejack-starter-kit/blob/v9/_data/strings.yml
[mybody]: https://github.com/hydecorp/hydejack-starter-kit/blob/v9/_includes/my-body.html

*[FOIT]: Flash of Invisible Text
*[GA]: Google Analytics
