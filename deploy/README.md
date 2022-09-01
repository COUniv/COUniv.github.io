---
layout: page
title: Deploy
description: >
  손쉽게 배포하기
hide_description: false
sitemap: false
permalink: /deploy/
---


## 설치하기 전에

먼저 사전에 Docker가 설치되어있어야 합니다. 도커 설치는 아래 링크를 통해 설치를 하시면 됩니다.   
[Docker Desktop for Windows and Mac](https://www.docker.com/products/docker-desktop)
{:.note}



## 설치 및 운용하기

우리 프로젝트는 기본적으로 모두 Docker Image를 사용합니다. 서비스를 실행 및 배포하는 방법은 매우 간단합니다. [COU Deploy](https://github.com/COUniv/COUDeploy) 에서 프로젝트를 받은 다음 terminal을 열고 docker-compose.yml이 있는 폴더에서 다음 명령어를 실행해주시면 됩니다.

```sh
docker-compose up -d
```

모두 설치가 완료되었다면 `http://localhost` 에 접속하시면 됩니다.


서비스 이용에 있어 설치 과정에서 Super Admin 권한을 갖는 계정이 생성됩니다. 아이디와 비밀번호는 각각 root, rootroot가 됩니다. 추후 서비스를 운용할 시 반드시 비밀번호를 변경하시기를 바랍니다.