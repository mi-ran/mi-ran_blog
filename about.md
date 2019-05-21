---
bg: "owl.jpg"
layout: page
title: "About"
crawlertitle: "Why and how this blog was created"
permalink: /about/
summary: "About this blog"
active: about
---
# My Working
***
## [synapsoft]
#### DocumentModel

워드, 슬라이드, 셀 등의 문서를 편집하는 프로젝트입니다. 웹오피스의 내부에 들어가는 문서편집 프로젝트입니다.

주로 워드와 셀의 편집을 작업하였습니다. 셀은 MS에서 제공하는 것처럼 함수, 조건부서식 등의 기능도 구현하였습니다.
- Tech
	- ProtoBuf
	- C++
	- CMake

#### Importer

MS 문서 및 한글 문서를 내부 모델로 바꾸는 프로젝트입니다. Importer에 의해서 내부 모델로 바뀐 문서는 DocumentModel에 의해 편집 될 수 있습니다.

이미지 뷰어, html 뷰어와 같이 문서를 오피스가 없어도 볼 수 있도록 하는 제품에 주로 함께 사용되는 프로젝트입니다.

xls(MS의 셀 포맷)과 docx(MS의 워드 포맷)을 주로 작업하였습니다. 그리고 Importer의 결과가 항상 같게 유지 되는지 확인하기 위해 테스트를 자동화하여, 품질을 유지하는 작업도 함께 수행하였습니다.
- Tech
	- C++
	- CMake
	- Python
	- Shell script

#### Exporter

외부 문서포맷을 내부 모델로 바꾸는 Importer와 반대로 내부 모델을 외부 문서포맷으로 바꾸는 프로젝트입니다. 주로 오피스에서 저장하기 기능으로 많이 사용됩니다.
- Tech
	- C++
	- CMake

*****

### SlackBot

슬랙을 통해 업무의 커뮤니케이션을 진행하고 있습니다. 장난감 삼아 slack봇을 만들어서 슬랙방에서 사용하고 있습니다.
주요기능은 노래 틀어주기(노래 제목만 입력), 알람, 인사하기, 도움말 등입니다.
구조적으로 기능을 추가하기에 힘들지 않게 만들었기 때문에 새로운 기능을 추가하기에 어렵지 않습니다.
- Tech
	- Python (Flask)

### ETC

- gitlab
	- 위의 프로젝트들은 gitlab으로 관리하고 있습니다. 하나의 브랜치가 master에 머지될 때마다 CI툴(Jenkins)를 통해 빌드가 문제없이 통과되는지 확인하는 작업을 거칩니다.
- CI(Jenkins)
	- 메모리 릭과 같은 문제가 발생하지 않는지, 매일 Jenkins를 이용해서 sanitizer를 돌려 확인하고 있습니다.
- 배포 자동화
	- 배포하는 로직을 스크립트로 관리하여 테그 이름만 입력하면 그에 맞게 각 프로젝트의 테그 브랜치를 따도록 관리 하고 있습니다.


*****

