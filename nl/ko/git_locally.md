---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-26"

keywords: Git source control, personal access token, Git repos

subcollection: ContinuousDelivery

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Git 소스 제어에 대해 작업할 로컬 클라이언트 설정
{: #git_local}


GitHub, GitHub Enterprise 또는 {{site.data.keyword.gitrepos}} 저장소에 있는 소스 코드를 로컬 또는 Eclipse Orion {{site.data.keyword.webide}}에서 관리하고 이에 대해 작업할 수 있습니다. 로컬로 작업하려면 Git 클라이언트(예: Git 명령행 인터페이스)를 사용하여 저장소를 복제하고 원하는 편집기로 코드를 편집하십시오. Eclipse에서 작업하는 경우 버전 제어를 위해 EGit 플러그인을 설치할 수 있습니다.

## 명령행에서 Git 프로젝트 복제


## 시작하기 전에
{: #git_before_clone}

1. 브라우저 외부에서 Git 서버에 액세스하려면 인증을 위한 개인 액세스 토큰 또는 SSH 키를 작성해야 합니다. 다음 표는 인증 설정을 위해 수행해야 할 작업을 표시합니다.

|Git 유형  |HTTPS 설정 |HTTPS 사용 |SSH 설정 |
|:-----------|:-------------|:------------|:-------------|
|Git Repos and Issue Tracking  |[개인 액세스 토큰](/docs/services/ContinuousDelivery?topic=ContinuousDelivery-git_working#create_pat) |Git Repos and Issue Tracking 사용자 이름(IBM ID 아님) 및 개인 액세스 토큰 |[SSH 키 구성](/docs/services/ContinuousDelivery?topic=ContinuousDelivery-git_working#creating-an-ssh-key) |
|공용 GitHub(github.com) |개인 액세스 토큰이 필요하지 않으나 개인 액세스 토큰을 설정하여 이를 사용할 수 있음 |GitHub 사용자 이름 및 비밀번호 또는 GitHub 사용자 이름 및 개인 액세스 토큰 또는 사용자 이름으로 된 개인 액세스 토큰 |[GitHub SSH 키 구성](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) |
|GitHub Enterprise |[개인 액세스 토큰](/docs/services/ghededicated?topic=ghededicated-getting-started#ghe_auth) |GitHub Enterprise 사용자 이름(IBM ID 아님) 및 개인 액세스 토큰 |[GitHub Enterprise SSH 키 구성](/docs/services/ghededicated?topic=ghededicated-getting-started#ghe_auth) |

SSH를 사용하려는 경우 모든 Git 서버에 단일 키를 재사용할 수 있습니다. 키를 작성하거나 찾아 이전 링크에 설명된 대로 각 서버에 키를 구성하십시오. 비밀번호 문구를 사용하여 키를 작성하는 경우 키를 사용할 때 비밀번호 문구를 요구하는 프롬프트가 표시됩니다.
{: tip}

2. Git 명령행을 사용할 경우 다음 단계를 완료하십시오.

    a. Git가 설치되어 있는지 확인하십시오. 명령행에 `git version`을 입력하십시오. Git가 설치되면 버전 번호가 표시되고 시작할 수 있습니다.

    b. Git가 설치되어 있지 않으면 [Git 웹 사이트로 이동하십시오![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://git-scm.com/downloads){: new_window}.

    c. 운영 체제에 맞는 버전을 다운로드하고 설치하십시오. 기본 설치 값을 사용할 수 있습니다.


### 프로젝트 복제
{: #git_clone}

데스크탑 도구를 사용하여 Web IDE 외부에서 저장소의 컨텐츠에 액세스할 수 있도록 Git 저장소를 복제하여 프로젝트 파일의 로컬 사본을 작성하십시오.

1. 도구 체인의 개요 페이지에서 복제할 저장소의 카드를 클릭하십시오.

2. 저장소 URL의 정보를 확보하십시오.

   a. GitHub에서 **복제 또는 다운로드**를 클릭하십시오. HTTPS를 사용하려면 **HTTPS 사용**을 선택하십시오.  SSH를 사용하려면 **SSH 사용**을 클릭하십시오. URL을 복사하려면 클립보드 아이콘을 클릭하십시오.

   b. Git Repos and Issue Tracking에서 **HTTPS** 또는 **SSH**를 선택하고 필드의 URL을 복사하십시오.

3. 명령행을 여십시오.

4. 디렉토리를 Git 저장소의 로컬 사본이 배치될 위치로 변경하십시오.

5. `git clone`을 입력하고 URL을 붙여넣기하여 Enter를 누르십시오.

6. 인증을 요구하는 프롬프트가 표시되면 이전 표에 정의된 대로 올바른 정보를 입력하십시오.


다운로드가 완료되면 저장소에 파일의 로컬 버전이 제공됩니다. Git 사용에 대한 자세한 정보는 [Git 문서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")]](http://git-scm.com/doc){: new_window}를 참조하십시오. 


## Eclipse 및 EGit 플러그인을 사용하여 저장소에 액세스
{: #git_egit}

Eclipse를 사용하고 소스 제어를 위해 Git를 사용하는 프로젝트를 보유하고 있는 경우 EGit 플러그인을 사용하여 Eclipse에서 저장소를 관리할 수 있습니다. EGit을 설치하고 구성하는 방법에 대한 자세한 정보는 [EGit 튜토리얼 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")]](http://eclipsesource.com/blogs/tutorials/egit-tutorial/){: new_window}을 참조하십시오. 

{{site.data.keyword.gitrepos}}를 사용하는 중에 문제점이 발생하는 경우에는 [{{site.data.keyword.gitrepos}}](/docs/services/ContinuousDelivery?topic=ContinuousDelivery-git_working#git_local) 문서를 참조하십시오. 
