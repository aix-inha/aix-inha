---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - python

toc_footers:
  - <a href='https://aix.inha.ac.kr/'>인하대학교 인공지능융합연구센터</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introduction

인하대학교 인공지능융합연구센터 (이하 ”AI 센터”)에 오신 것을 환영합니다. 저희 AI 센터는 최첨단 GPU 서버 센터를 구축하여 A100, A6000, A40 등의 고성능 컴퓨팅 자원을 인하대학교 학생 및 교수님들, 그리고 기업체 및 인천시민 여러분께 무상으로 제공하고 있습니다. 이를 통해 인공지능 연구와 개발에 필요한 모든 고성능 계산 작업을 지원하고자 합니다.
<br/>작성된 튜토리얼을 통해 원활한 사용과 연구에 도움이 되기를 진심으로 바라겠습니다. 감사합니다.

<aside class="notice">
AI 센터의 자원을 이용하시려면 먼저 인하대학교 인공지능융합연구센터 홈페이지를 통해 계정을 신청하시기 바랍니다. 계정 승인 후, 개인별 혹은 팀별로 할당된 자원을 이용하실 수 있습니다.
</aside>

공지 수신 및 기술적인 문제나 사용법에 대한 질문이 있으시면, [디스코드 채널](https://discord.gg/PyBkTDz4Mp)에 입장하여 연락주시기 바랍니다.
<br/>추가로, 긴급 공지 사항을 위해 만들어진 [카카오오픈채팅방](https://open.kakao.com/o/gNVmxJof)에 반드시 참여를 부탁드립니다.

### System Overview
Simple Linux Utility for Resource Management (이하 “Slurm”) 을 통해 GPU 자원을 제공하고 있습니다. Slurm은 클러스터 환경의 자원 관리 시스템으로, 사용자의 요청에 컴퓨팅 자원을 할당합니다.  
<br/> 사용자는 자원을 할당 받은 후, Conda와 Singularity 컨테이너 솔루션을 통해 사용자가 원하는 개발 환경에서 컴퓨팅 자원을 사용 할 수 있습니다.

자원이 모두 사용 중일 때는 대기를 해야하며, 자원이 확보될 시 Slurm이 대기하고 있던 사용자에게 할당해줍니다. <br/>
12시간 이상 GPU 사용이 없을 시 작업이 취소 될 수 있습니다.

### Available GPUs
AI 센터에서는 11개의 GPU 서버 (56 GPUs) 를 제공하고 있습니다. 

| GPU 타입 | GPU 메모리 | GPU 서버 대수 | 서버 당 GPU 카드 개수 |
|----------|------------|-----------------------|---------------|
| A100     | 40 GB      | 4                     | 4             |
| A40      | 48 GB      | 3                     | 8             |
| A6000    | 48 GB      | 4                     | 4             |


<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# How to use

## SSH Login
> "yourID"를 본인의 ID로 입력하여 SSH 연결하시길 바랍니다.
```shell
ssh "yourID"@165.246.75.159
```


사용자는 부여된 ID와 PW를 사용하여 SSH 연결을 통해 Login Node-1에 접속한 후, Slurm 시스템에게 GPU 자원 할당을 신청 할 수 있습니다.
<br/> SSH 연결은 Windows PowerShell, Ubuntu Terminal, MobaXterm 등 프로그램을 통해 사용 할 수 있습니다.


## 자원 신청


## File Uploads
파일 업로드는 본인 계정의 이름으로 된 폴더에 할 수 있습니다.<br/>
파일 업로드는 GPU 자원을 할당 받지 않고도 가능하며,

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten


```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```


> The above command returns JSON structured like this:


This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten


```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```


> The above command returns JSON structured like this:


This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

