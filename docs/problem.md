---
layout: page
title: Problem
description: >
  Problem Documentation
hide_description: true
sitemap: false
---

코딩 문제와 관련한 문서입니다.

0. problem docs table
{:toc}


## Summary
기본적으로 문제를 생성하고 관리할 수 있는 권한은 Admin, Super Admin만 가능합니다. 관리 하는 방법은 `계정 관리 -> Management -> 문제` 에서 가능합니다.

Admin의 경우 총 3가지 타입의 문제 권한이 주어집니다. 이 권한은 문제를 관리할 수 있는 카테고리 권한도 포함됩니다. **권한 없음**의 경우 일반사용자와 마찬가지로 문제를 생성할 수 있는 권한이 없습니다. **본인 권한**의 경우 문제 생성 및 삭제가 가능하나 그 권한은 본인이 만들고 생성한 문제로 제한됩니다. **모든 권한**의 경우 모든 문제에 대한 권한이 부여됩니다. 이러한 권한 조정은 Super Admin 계정에 의해 사용자 관리영역에서 조정 할 수 있습니다.
{:.note}


## Make a Problem
문제를 생성하기 위한 사전 준비로는 **Tag**와 **TestCase**가 필요합니다. Tag의 생성 및 관리는 아래 링크를 참고하시면 됩니다.
 
[Tag 바로가기](#tag) 
{:.note}



### TestCase Format
기본적인 테스트 케이스 파일은 ```.in```과 ```.out```의 확장자로 구성됩니다. ```.in```확장자를 갖는 파일은 입력 파일로 채점할 때 입력으로 주어지는 데이터들이 있는 파일이며, ```.out``` 확장자를 갖는 파일은 출력 파일로, 입력에 따른 요구되는 출력에 대한 파일로 채점을 통해 정답 혹은 오답을 판단하는 기준의 파일이 됩니다.

각 테스트 케이스 파일 이름은 숫자로 구성되어야 합니다. 예로들어 ```1.in```, ```2.in```과 ```1.out```, ```2.out``` 이런식으로 같은 숫자에 입력과 출력이 쌍으로 이루어져야 합니다.

각 테스트 케이스 파일 생성이 완료되었다면 ```.zip``` 으로 압축을 해야 합니다.
이 때 주의해야 할 점은 **반드시 테스트 케이스 파일을 압축 폴더의 root 디렉토리에 넣어야 합니다.**

<br />

올바른 예 :
```zsh
> pwd
/temp/testcase

> tree
.
├── 1.in
├── 1.out
├── 2.in
└── 2.out

0 directories, 4 files
```

<br />

잘못 된 예:

```zsh
> pwd
/temp/testcase

> tree
.
└── 1
│   ├── 1.in
│   └── 1.out
└── 2
    ├── 2.in
    └── 2.out

2 directories, 4 files
```

<br />

올바른 예시 대로 구성했다면 이제 테스트 케이스를 ```.zip```으로 압축해야 합니다.

```zsh
> zip testcase.zip ./{*.in,*.out}
  adding: 1.in (stored 0%)
  adding: 2.in (stored 0%)
  adding: 1.out (stored 0%)
  adding: 2.out (stored 0%)
```

<br />

압축 된 패키지 내용을 보면 다음과 같습니다.

```zsh
> testcase unzip -v testcase.zip
Archive:  testcase.zip
 Length   Method    Size  Cmpr    Date    Time   CRC-32   Name
--------  ------  ------- ---- ---------- ----- --------  ----
       3  Stored        3   0% 01-01-2022 00:00 00000000  1.in
       3  Stored        3   0% 01-01-2022 00:00 00000000  2.in
       1  Stored        1   0% 01-01-2022 00:00 00000000  1.out
       1  Stored        1   0% 01-01-2022 00:00 00000000  2.out
--------          -------  ---                            -------
       8                8   0%                            4 files
```

압축이 제대로 된 것 같으면서도 파일 형식이나 파일 개수가 틀리다는 메시지가 뜨면 숨김 파일이 압축되어 있는지 확인 할 필요가 있습니다.Windows의 $RECYCLE.BIN, Mac의 .DS_Store, Linux의 1.in~.1.in.swp 파일이 있을 수 있습니다.
{:.note}

<br />

테스트 케이스 그룹의 수를 줄이기 위해 가능한 여러 테스트 케이스를 하나의 파일로 병합하는 것이 좋습니다. 그러면 질문 판단 성능이 향상되고 사용자 코드의 실행 시간이 어느 정도 단축되는데 도움이 됩니다.
{:.note}

### Problem Format

문제 생성을 누르면 문제를 만들기 위한 기본 양식이 나옵니다. 해당 양식에 맞추어 문제를 생성하면 됩니다.

#### Display ID

<span style="color:#EE2E03;">특별한 경우가 아니면 해당 옵션은 건드리지 않는 것을 추천합니다.
이후 Display ID가 충돌을 일으키거나 잘못된 번호 입력으로 인해 제대로 표현되지 않을 수 있습니다.</span>
{:.note}

사용자에게 보여지는 문제 번호를 설정할 수 있습니다. 기본적으로 1000번부터 자동 할당되어 번호가 시작되며, 각 번호는 고유해야 합니다. 새로운 문제 추가시 1씩 증가하게 됩니다.


#### 제목
사용자에게 보여질 문제 제목을 입력폼입니다.

#### 문제 설명
사용자에게 문제에 대한 설명이 보여질 입력폼입니다.

#### 입력 설명
문제 설명에 의한 알고리즘에 대해 입력 형식이 어떻게 주어지는지를 설명하는 입력폼입니다.

#### 출력 설명
문제 설명에 의한 알고리즘에 대해 출력 형식에 대해 설명하는 입력폼입니다.

#### 시간 제한
문제 설명에 의한 알고리즘에 대해 수행 시간 제한하는 옵션입니다. C언어를 기준으로 하며, 그 외 언어는 해당 값에서 평균 수행시간을 고려하여 옵션이 자동 조정됩니다.
이는 실제 사용자에게 보여지는 시간이 아닌 백엔드에서 수행된 시간을 의미합니다.

#### 메모리 제한
문제 설명에 의한 알고리즘에 대해 메모리 제한하는 옵션입니다. C언어를 기준으로 하며, 그 외 언어는 해당 값에서 평균 메모리 사용량을 고려하여 옵션이 자동 조정됩니다.
이는 실제 사용자에게 보여지는 메모리 사용량이 아닌 백엔드에서 수행된 메모리 사용량을 의미합니다.


#### 난이도
해당 문제의 난이도를 설정할 수 있습니다. 해당 난이도는 추후 세부적으로 더 추가 될 예정입니다.


#### Visible
현재 문제를 홈페이지에 게시를 할지를 결정할 수 있습니다.


#### Share Submission
사용자들이 제출한 소스코드에 대해 타인의 접근을 허가하도록 제출 코드를 공유를 허용할지 말지를 설정할 수 있습니다.

#### 태그
문제의 Tag를 다는 곳 입니다. Tag의 생성 및 관리는 해당 링크를 참고하시면 됩니다. [Adding a Tag](#adding-a-tag).


#### 언어
제출 가능 언어들을 선택할 수 있습니다. 기본적으로는 C, C++, Java, Python2, Python3, Go, JavaScript 모두 허용하고 있으나, 일부 비허용을 하고싶은 경우 체크박스를 해제해주시면 됩니다.


#### 예제 입력 및 출력
실제 입력되는 데이터 양식과 같게 예시 데이터와 출력 데이터를 보여주는 입력 폼입니다.


#### Hint
문제에 대한 힌트를 작성할 수 있는 폼입니다. 필수는 아닙니다.


#### Code Template
사용자가 특정 함수내에서 작성할 수 있도록 하고싶다거나, 특정 언어에서 특정 폼을 유지하고 싶은 경우 해당 템플릿을 사용하시면 됩니다.
해당 템플릿을 작성하면, 이후 사용자가 문제를 제출하고자 할 때 해당 문제에서 체크한 언어의 경우 작성한 Template 폼에 맞추어 미리 띄워줍니다.

#### Special Judge
특별 채점에 관하여 채점 방식을 코드로 작성한 뒤 해당 코드에 맞춰 채점이 진행되는 방식입니다. 자세한 내용은 [Special Judge](#special-judge-1) 섹션을 참고하시기를 바랍니다.

#### ACM and OI
채점 방식을 설정하는 모드입니다. 현재는 ACM 모드만 활성화 되어있으나, 추후 OI모드도 추가 될 예정입니다. 두 모드의 차이는 다음과 같습니다.
- ACM
  - 국제 대학생 프로그래밍 대회인 ACM-ICPC의 규칙을 따릅니다. 이 모드에서는 테스트케이스로 주어진 **모든** 테스트를 통과를 해야만 정답으로 처리가 됩니다. 하나의 테스트 케이스라도 통과되지 않을시 오답으로 처리됩니다.
- OI
  - OI 모드는 각 테스케이스 별로 채점을 하여 점수를 부여하는 방식입니다.

#### TestCase
```.in```과 ```.out``` 확장자로 이루어진 테스트케이스 파일들이 묶인 ```.zip```파일로 압축된 파일을 업로드를 하면, ```.zip```을 인식하여 내부 각 테스트케이스 파일들이 리스트로 업로드가 됩니다.
테스트 케이스를 만드는 방법에 대해서는 [TestCase format](#testcase-format)을 참고하시기를 바랍니다.

#### Source
예시 소스코드를 입력할 수 있는 입력 폼입니다. 필수 입력은 아닙니다.




## Tag

문제를 생성하는데 필요한 Tag를 생성하고 이를 관리할 수 있습니다. Tag는 문제의 성질 및 성격을 분류하여 사용자들이 컨텐츠 접근에 용이하도록 하기 위한 장치로서 작동합니다.
이로인하여 최소 한 개 이상의 Tag를 필요로 하기 때문에 기존에 생성해둔 Tag가 없다면 우선 Tag를 생성해야 합니다.


### Adding a Tag
태그를 생성하는 방법은 매우 간단합니다. `문제 > 문제 태그`에서 **문제 태그 생성** 버튼을 눌러 폼에 맞추어 등록하면 됩니다.


<!-- Type       | Title
-----------|------
Categories | Welcome to Jekyll¬ 07 Apr 2017 **in** Jekyll / Update
Tags       | Welcome to Jekyll¬ 07 Apr 2017 **on** Jekyll, Update
Both       | Welcome to Jekyll¬ 07 Apr 2017 **in** Jekyll / Update **on** Jekyll, Update
{:.scroll-table-small}

You can adjust these in [`_data/string.yml`][strings]. -->

## Special Judge

### Special Judge란
특별 채점은 제출 된 프로그램의 출력이 정확히 일치하지 않을 때 사용할 수 있는 기능입니다.

### 사용 목적
문제에서 요구하는 답변에 대한 출력이 고유할 수 없을 때 사용됩니다. 예로들어 부동소수점의 결과를 필요로 할 때가 있습니다.

부동소수점의 경우 오차 및 각 언어별 출력 길이가 다르기 때문에 답변이 고유하지 않을 수 있습니다. 예로들어 C++의 경우 cout을 사용 할 경우 전체 자리수가 6자리로 고정되어 출력되며, 또 다른 예로 부동소수점(IEEE 754 기준) 단정밀도의 경우 안전하게 사용할 수 있는 정밀도는 $$ log_{10} (2^{24}) $$ 로 7~8자리, 배정밀도의 경우 $$ log_{10} (2^{53}) $$ 으로 15~16자리로 정밀도 차이가 다릅니다. 이럴 때 Special Judge를 사용하여 특정 유효 자리수까지만 채점하도록 할 수 있습니다.


### Special Judge Program 작성 예시

```c
#include <stdio.h>

#define AC 0
#define WA 1
#define ERROR -1

int spj(FILE *input, FILE *user_output);

void close_file(FILE *f){
    if(f != NULL){
        fclose(f);
    }
}

int main(int argc, char *args[]){
    FILE *input = NULL, *user_output = NULL;
    int result;
    if(argc != 3){
        printf("Usage: spj x.in x.out\n");
        return ERROR;
    }
    input = fopen(args[1], "r");
    user_output = fopen(args[2], "r");
    if(input == NULL || user_output == NULL){
        printf("Failed to open output file\n");
        close_file(input);
        close_file(user_output);
        return ERROR;
    }

    result = spj(input, user_output);
    printf("result: %d\n", result);
    
    close_file(input);
    close_file(user_output);
    return result;
}

int spj(FILE *input, FILE *user_output){
    /*
      parameter: 
        - input， 프로그램 입력을 위한 파일 포인터
        - user_output， 사용자 출력 파일에 대한 포인터
      return: 
        - 사용자의 답변이 맞으면 AC로 복귀
        - 사용자의 답변이 틀리면 WA 반환
        - 메모리 할당 실패와 같은 자신의 오류를 적극적으로 포착하면 ERROR를 반환
      demo:
      int a, b;
      while(fscanf(f, "%d %d", &a, &b) != EOF){
          if(a -b != 3){
              return WA;
          }
      }
      return AC;
     */
}
```

실행할 때 채점 결과는 main함수의 반환 값에 따릅니다. 참고로 OJ의 문제판단 프로그램도 샌드박스에서 실행되며, 제한시간은 문제제한 시간의 3배, 메모리 제한은 1G입니다.
{:.note}

Continue with [Category](category.md){:.heading.flip-title}
{:.read-more}