TIL 9.16
<h2>Amazon Web Service</h2>
<h4>클라우드 컴퓨팅의 장점</h4>
필요할 때마다 컴퓨팅 능력을 유연하게 조절할 수 있습니다.

고정적인 비용이 들어가는 온프레미스와는 달리 사용한 만큼의 요금만 지불하면 됩니다.

컴퓨터의 스냅샷("이미지"라고 부릅니다) 을 이용해 다른 컴퓨터로 즉시 이주(migration)가 가능합니다.

<h4>클라우드 컴퓨팅의 단점</h4>
클라우드 서비스 종속

서비스에 영향을 미침

대표적인 클라우드 서비스의 형태는 SaaS, IaaS, PaaS 세 가지입니다.

SaaS는 Software as a Service의 약자입니다.

클라우드 제공자가 당장 사용 가능한 소프트웨어를 제공하는 경우 대부분 SaaS에 해당합니다.

PaaS는 Platform as a Service의 약자입니다.

클라우드 제공자가 데이터베이스, 개발 플랫폼까지 제공하는 경우 대부분 PaaS에 해당합니다.

IaaS는 Infrastructure as a Service의 약자입니다.

클라우드 제공자가 가상 컴퓨터까지 제공하는 경우 대부분 IaaS에 해당합니다.

<h4>AWS IAM</h4>
사용자, 그룹의 권한을 부여하고 관리가 가능할수 있도록 해주는 서비스 입니다.

<h4>IAM을 사용하는 이유</h4>
권한을 세분화 하지 않는 경우 모든 리소스에 접근하기 위한 계정을 여러 인원들이 공유 가능합니다.

다른 부분에서 권한을 세분화 하는 이유를 찾을수 있습니다.

대체로 이런 서비스, 리소스들은 권한을 가지지 못한 사람들이 접근할수 없습니다.
만약 이런 서비스, 리소스를 대상으로한 공격이 있다 하더라도 특정 권한이 없는한 공격이 성사될수 없습니다.

이러한 이유로 권한을 세분화하여 특정 그룹, 특정 사용자들만 특정 리소스에 접근할수 있도록 하는것이 일반적입니다.

<h4>AWS CLI</h4>
CLI를 이용하면 AWS 관리 콘솔의 기능 대다수를 로컬 터미널에서 사용할수 있습니다.
CLI를 사용하기 위해서는 권한을 부여받은 IAM 사용자의 정보가 필요하며 운영체제에 맞는 AWS CLI를 설치해야 합니다.

brew를 이용한 설치
```
$ brew install awscli
```

aws configure 명령을 통해서 기본 액세스키, 시크릿키, 리전을 설정한다.
```
$ aws configure
```

AWS Access Key ID [None]:
AWS Secret Access Key [None]:
Default region name [None]: .ex)ap-northeast-2
Default output format [None]:
AWS s3 Sync 명령어로 업로드하기
```
$ aws s3 sync ./ s3://bucketName
```
upload: test.txt to s3://bucketName/test.txt
```
$ aws s3 sync s3://bucketName ./
```
download: s3://bucketName/test.txt to test.txt
```
$ aws s3 sync s3://bucketName s3://bucketName
```
copy: s3://mybucket/test.txt to s3://bucketName/test.txt
AWS S3 버킷 관련 명령어
버킷 목록 조회
```
$ aws s3 ls
```
버킷 생성
```
$ aws s3 mb s3 ://{bucketName}
```
버킷 삭제
```
$ aws s3 rb s3 ://{bucketName}
```
오브젝트 관련 명령어
오브젝트 업로드(동기화)
aws s3 sync {로컬파일 경로} s3 ://{버킷이름}
오브젝트 목록 조회
aws s3 ls s3://{버킷이름}
오브젝트 삭제
aws s3 rm s3://{버킷이름/오브젝트/경로}
