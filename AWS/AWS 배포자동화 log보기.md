<h2>빌드 로그 파일 확인</h2>
<h3>CodeBuild 콘솔을 통한 로그 파일 확인</h3>

1. CodeBuild 서비스의 메인 콘솔로 접속합니다.


2. 사이드바에 프로젝트 빌드 탭을 클릭한 뒤, 파이프라인을 구축하며 생성한 빌드 프로젝트를 클릭합니다.


3. 실패한 빌드 실행 기록을 클릭합니다.


4. 빌드 로그를 보고 발생한 오류를 확인 및 해결합니다.


<h3>CloudWatch를 통한 로그 파일 확인</h3>

1. CloudWatch의 메인 콘솔에 접속합니다.


2. 사이드 바에 있는 로그 그룹을 클릭합니다.


3. 생성한 빌드 프로젝트 이름을 찾아 클릭합니다. '/aws/codebuild/빌드 프로젝트 이름' 으로 구성된 로그 그룹을 찾습니다.


4. 가장 최신 버전의 로그 스트림을 클릭합니다.


5. CodeBuild 콘솔로 확인했던 빌드 로그가 CloudWatch에도 저장된 것을 확인할 수 있습니다.
