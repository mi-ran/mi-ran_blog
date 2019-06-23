---
bg: "owl.jpg"
layout: page
title: "Career"
crawlertitle: "My working"
permalink: /career/
summary: "my career"
active: career
---
<head>
	<title> My Working</title>
	<meta charset="utf-8"/>
</head>
<body>
	<!-- Synap Viewer -->
	<h1>Synap Viewer<p style="font-size:10px">2016.01 ~ </p></h1>
	<img src="/assets/images/synapViewer_icon.png" style="float:right;" width="200px"/>
	<p class="bodyText"> 사이냅 뷰어는 MS문서 및 한글 문서의 내용을 오피스 프로그램 없이 쉽게 확인할 수 있도록 하는 프로그램입니다. 2016년 부터 개발 중이며 점점 기능을 늘려가는 중입니다. 사이냅 뷰어 중 제가 주로 개발하는 부분은 DocumentModel과 Importer입니다.</p>
	<h3>DocumentModel <p style="font-size:10px">문서를 쉽게 랜더링 하기 위한 내부 모델</p></h3>
	<p class="bodyText">c++와 protobuf를 이용하여 만들었습니다.</p>
	<h3>Importer <p style="font-size:10px">문서를 내부모델로 바꾸는 프로젝트</p></h3>
	<p class="bodyText">c++을 이용하여 만들어졌으며, cmake로 빌드를 관리합니다. 품질 관리를 위해 shell script, python, Jenkins를 이용해서 리그레션 테스트를 수행하고 있습니다. 또 코드의 품질을 위해 docker를 이용해서 sanitizer를 매일 확인 하고 있습니다.</p>
	<hr>
	<!-- Synap Office -->
	<h1>Synap Office <p style="font-size:10px">2016.01 ~ </p></h1>
	<img src="/assets/images/synapOffice_icon.png" style="float:right;" width="200px"/>
	<p class="bodyText"> 사이냅 오피스는 설치가 필요없이 언제나 문서를 쉽게 편집할 수 있도록 합니다. 현재 네이버 오피스로 서비스되고 있으며, word/slide/cell/form의 포맷을 지원합니다. 오피스를 ms문서, 아래아한글 등의 문서를 내부 모델로 변경하여 편집합니다. 제가 개발에 참여한 부분은 Importer와 DocumentModel, Exporter 부분입니다. </p>
	<h3>Importer <p style="font-size:10px">문서를 내부모델로 바꾸는 프로젝트</p></h3>
	<p class="bodyText">c++을 이용해서 만들었으며, cmake로 빌드합니다. 오피스에서 문서를 열면 임포터는 내부모델을 만들어서 반환하게 됩니다.</p>
	<h3>DocumentModel <p style="font-size:10px">문서를 쉽게 편집 할 수 있게 하기 위한 내부 모델</p></h3>
	<p class="bodyText">c++와 protobuf를 이용하여 만들었습니다. DocumentModel 프로젝트는 내부 모델만이 아니라 문서를 편집 할 수 있도록 편집 api를 함께 제공합니다. 편집 api들은 cxx테스트를 이용해서 테스트 코드를 작성하여 관리 하고 있습니다.</p>
	<h3>Exporter <p style="font-size:10px">사이냅 오피스에서 편집한 문서를 다시 저장하는 프로젝트</p></h3>
	<p class="bodyText">c++을 이용하여 만들었으며, cmake로 빌드합니다. 오피스에서 문서를 편집한 후 다시 문서를 저장할 때 사용하는 프로젝트로, 내부 모델을 다시 ms 또는 아래아한글의 포맷으로 바꾸어 저장해 줍니다. 이렇게 저장된 문서는 ms office,  한글과 컴퓨터 프로그램으로 열어볼 수 있습니다.</p>
	<hr>
	<!--Synap Editor -->
	<h1>Synap Editor <p style="font-size:10px"> 2017.11 ~ </p></h1>
	<img src="/assets/images/synapEditor_icon.png" style="float:right;" width="200px"/>
	<p class="bodyText"> 사이냅 에디터는 문서임포트 기능을 탑제한 에디터입니다. 현재 워드(ms, 아래아한글), 셀 문서를 임포트 해서 사용할 수 있습니다. 문서 임포트 기능은 기존의 Importer 프로젝트의 결과물을 에디터에 맞도록 수정하는 방향으로 구현되었습니다.</p>
	<h3>SedocConverter <p style="font-size:10px">임포터의 결과를 에디터에 맞도록 수정하는 프로젝트</p></h3>
	<p class="bodyText">c++을 이용하여 만들었으며, 에디터에서 표현할 수 없는 기능들을 제외하고 도형이나 워드아트 등을 이미지로 바꾸는 등의 역할을 합니다.</p>
</body>

