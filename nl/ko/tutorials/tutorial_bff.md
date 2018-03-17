---

copyright:
  years: 2016, 2017
lastupdated: "2017-11-02"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# BFF 기본 스타터의 엔드-투-엔드 튜토리얼
{: #tutorial}

다음의 엔드-투-엔드 튜토리얼에서는 BFF 기본 스타터에서 프로젝트를 작성하는 단계를 안내합니다. 여기에는 전제조건 도구의 설치 및 프로젝트 코드를 실행하는 단계가 포함됩니다. 


## 개발자 도구 설치
{: #dev_tools}

[전제조건 개발자 도구 ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](get_code.html#prereq-dev-tools){: new_window}를 설치했는지 확인하십시오. 


## 프로젝트 작성 방법 선택
{: #choose_how}

웹 기반 [{{site.data.keyword.dev_console}}](#create-devex)을 사용하거나 명령어 방식 [{{site.data.keyword.dev_cli_notm}}](#create-cli)을 통해 프로젝트를 작성합니다. 프로젝트가 작성된 후에 [프로젝트를 실행](#running-bff)할 수 있습니다.


## {{site.data.keyword.dev_console}}을 사용하여 프로젝트 작성
{: #create-devex}

1. {{site.data.keyword.Bluemix}} {{site.data.keyword.dev_console}}에서 프로젝트를 작성하십시오. 

	1. {{site.data.keyword.dev_console}}의 [**시작하기** ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.ng.bluemix.net/developer/getting-started/) 페이지에서 **프로젝트 작성**을 클릭하십시오. 

		또는 **프로젝트** 페이지에서 **프로젝트 작성**을 클릭할 수 있습니다. 

	2. **BFF(Backend for Frontend)**를 선택하고 **다음**을 클릭하십시오. 

	3. **기본 백엔드**를 선택하고 **다음**을 클릭하십시오. 

	4. 프로젝트 이름을 입력하십시오. 이 튜토리얼의 경우 `BFFProject`를 사용하십시오.    

	5. 예를 들면, 사용자의 이니셜에 `-devhost`를 덧붙여 고유 호스트 이름을 입력하십시오. 예:
	
	 ```
	 abc-devhost
	 ``` 

	6. 언어 플랫폼을 선택하십시오. 이 튜토리얼의 경우 `Node`를 사용하십시오. 
   
	7. **작성**을 클릭하십시오.

2. 선택사항: 데이터 기능을 추가하십시오. 

	1. **프로젝트 개요** 페이지에서 **데이터**에 대한 **보기**를 클릭하십시오. 

      **기능 > 데이터** 페이지에서 **작성** 또는 **기존 추가**를 선택할 수도 있습니다. 

   2. 서비스 이름을 입력하고 **작성**을 클릭하십시오. 

3. 프로젝트 코드를 생성하십시오. 

	1. **프로젝트 개요** 페이지에서 **코드 가져오기**를 클릭하여 언어를 선택하십시오. 
   
		또는 **코드** 페이지를 클릭할 수 있습니다.
      
	2. **코드 생성**을 클릭하십시오. 
   
	3. 프로젝트 코드 생성이 완료되면 **코드 다운로드**를 클릭하여 프로젝트 아카이브를 다운로드하십시오.

4. 다운로드된 프로젝트 관련 작업을 시작하십시오. 

	1. 아카이브된 파일을 펼치십시오. 
	
	2. 새 프로젝트 디렉토리로 이동하십시오. 
	
	3. {{site.data.keyword.dev_cli_notm}}을 사용하여 계속 진행하십시오. 

5. 선택사항: 새 언어를 생성하도록 [프로젝트를 업데이트하십시오](project_overview_page.html#update_language). 


## {{site.data.keyword.dev_cli_notm}}을 사용하여 프로젝트 작성
{: #create-cli}

1. [{{site.data.keyword.dev_cli_short}}](dev_cli.html)을 설치해야 합니다. 

2. 터미널 프롬프트에서 원하는 로컬 디렉토리로 이동하여 다음 명령을 실행하십시오. 
  
	```
	bx dev create
	```
	{: codeblock}
	
3. 프롬프트가 표시되면 다음 값을 제공하십시오. 

	* 패턴 선택: 3(BFF(Backend for Frontend))
	* 스타터 선택: 1(기본 백엔드)
	* 언어 선택: 1(Node)
	* 프로젝트의 이름 입력: `BFFProjectCLI`
	* 프로젝트의 호스트 이름 입력: `abc-devhost`
	  * 예를 들면, 사용자의 이니셜에 `-devhost`를 덧붙여 고유 호스트 이름을 입력하십시오. 예:
	
	     ```
	     abc-devhost
	     ```
	  
4. `BFFProjectCLI`가 저장된 후에 `BFFProjectCLI` 폴더로 이동하십시오. 

5. 사용자 코드를 추가한 후 프로젝트 빌드하고 실행하십시오. 
 
	1. 다음 명령으로 프로젝트를 빌드하십시오. 

		```
		bx dev build
		```
		{: codeblock}
		 
	2. 다음 명령을 사용하여 프로젝트를 실행하십시오. 

 		```
		bx dev run
		```
		{: codeblock}


## BFF 프로젝트 실행
{: #running-bff}

필요한 빌드 도구를 설치하는 경우 로컬로 사용자의 호스트 시스템에서 애플리케이션을 실행하거나 {{site.data.keyword.dev_cli_notm}}에서 사용 가능한 컨테이너 지원을 사용하여 실행할 수 있습니다.


### IBM Cloud 플러그인 사용
{: #using-blumix}

1. 현재 프로젝트 디렉토리에서 프로젝트를 빌드하려면 다음 명령을 입력하십시오.

   ```
   bx dev build
   ```
   {: codeblock}

2. 현재 프로젝트 디렉토리에서 프로젝트를 실행하려면 다음 명령을 입력하십시오.

   ```
   bx dev run
   ```
   {: codeblock}

3. 다음으로 서버에서 curl을 실행할 수 있습니다.

   ```
   curl http://localhost:8080
   ```
   {: codeblock}

4. 다음 위치에서 서버의 API 문서를 볼 수 있습니다.

   ```
   http://localhost:8080/swagger/api
   ```
   {: codeblock}

5. 다음 위치에서 서버의 API를 탐색할 수 있습니다.

   ```
   http://localhost:8080/explorer
   ```
   {: codeblock}
