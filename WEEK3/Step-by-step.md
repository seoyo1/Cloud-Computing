## Overview
 - Python에서 AWS의 Rekognition을 이용하여 이미지에서 사람의 얼굴을 인식하여 감정을 분석하는 프로그램을 제작합니다.

## IAM 계정 생성
```
Amazon Rekognition과 같은 AWS의 서비스는 액세스 할 때 자격 증명을 제공해야합니다.
이는 서비스가 해당 서비스가 소유 한 리소스에 액세스 할 수있는 권한이 있는지 여부를 확인할 수 있도록하기위한 것입니다.
콘솔에 암호가 필요합니다.</br> AWS 계정에 대한 액세스 키를 만들어 AWS CLI 또는 API에 액세스 할 수 있습니다.
그러나 AWS 계정에 대한 자격 증명을 사용하여 AWS에 액세스하지 않는 것이 좋습니다.</br> 대신 다음과 같이하는 것이 좋습니다.
```
 - AWS ID 및 액세스 관리 (IAM)를 사용하여 IAM 사용자를 생성
   - AWS 계정을 사용하여 IAM 콘솔에 AWS 계정 루트 사용자로 로그인합니다.
   - 탐색 창에서 사용자를 선택한 다음 사용자 추가를 선택합니다
   - 사용자의 이름을 입력하고 AWS Management Console 액세스를 체크하고 사용자 지정 비밀 번호를 설정한 다음 텍스트 상자에 새 암호를 입력합니다.</br> 다음: 권한을 누르세요. </br>
  ![Style Images](https://github.com/seoyo1/Cloud-Computing/blob/master/Capture/step1.png)
   - 상단에 그룹에 사용자를 추가를 선택하고 그룹 생성을 선택 하십시오
   - 그룹 이름을 설정하고 정책 필터에서 AWS 관리 – 직무로 설정하고 AdministratorAccess를 선택합니다. 그런 다음 그룹 생성을 선택 하십시오.</br>
  ![Style Images](https://github.com/seoyo1/Cloud-Computing/blob/master/Capture/step2.png)
  ![Style Images](https://github.com/seoyo1/Cloud-Computing/blob/master/Capture/step3.png)
  
 - AWS CLI 및 AWS SDK 설정
```
다음 단계에서는이 설명서의 예제에 사용되는 AWS CLI (Command Line Interface) 및 AWS SDK를 설치하는 방법을 보여줍니다.
AWS SDK 호출을 인증하는 여러 가지 방법이 있습니다.
이 가이드의 예제는 AWS CLI 명령 및 AWS SDK API 작업 호출에 기본 자격 증명 프로필을 사용한다고 가정합니다.
``` 
   - 사용할 AWS CLI 및 AWS SDK를 다운로드 하여 설치하십시오.</br>
   [Python용 sdk] (https://boto3.amazonaws.com/v1/documentation/api/latest/index.html)</br>
   [AWS CLI] (https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)</br>
   
   - IAM 사용자 만들기에서 만든 사용자의 액세스 키를 만듭니다.
     - IAM 콘솔의 탐색 창에서 사용자를 선택합니다.
     - IAM 사용자 만들기에서 만든 사용자 이름을 선택합니다. 
     - 보안 자격 증명 탭을 선택합니다.
     - 액세스 키 생성을 선택 합니다. 그런 다음 .csv 파일 다운로드를 선택하여 액세스 키 ID와 비밀 액세스 키를 컴퓨터의 CSV파일에 저장합니다.</br>
     
   ![Style Images](https://github.com/seoyo1/Cloud-Computing/blob/master/Capture/step4.png)</br>
   
   - AWS CLI를 설치한 다음 명령 프롬프트에서 aws configure를 입력하여 AWS SDK에 대한 자격 증명 및 지역구성을 설정합니다.</br>
   ![Style Images](https://github.com/seoyo1/Cloud-Computing/blob/master/Capture/step5.png)
   
 - S3 버킷 생성
```
이미지를 인식하기 위해 파일을 업로드 시킬 S3 버킷을 생성합니다
```
  - AWS 서비스에서 스토리지의 S3를 선택합니다.
  
  - 버킷 만들기를 클릭하여 버킷이름을 설정하고 다음을 눌러 버킷을 생성합니다</br>
  ![Style Images](https://github.com/seoyo1/Cloud-Computing/blob/master/Capture/step6.png)</br>
  
- 이후엔 Python을 통해 코드작업을 합니다.
[코드](https://github.com/seoyo1/Cloud-Computing/blob/master/WEEK3/rekog%20pyhton.txt)


