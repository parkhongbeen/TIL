## Crontab

오늘은 간단하게 crontab을 사용하는 법에 대해서 간략하게 정리하려고 합니다.

1. 원하는 위치에 로그가 담길 파일을 작성합니다.

![image-20200811214344692](https://user-images.githubusercontent.com/53684676/89902156-11ddc700-dc21-11ea-9e2c-ed74a984e19a.png)

2. 별도로 작성할 내용은 없으니 `esc`를 누른 후 다음과 같이 파일을 쓰고 종류해줍니다.

![image-20200811214331518](https://user-images.githubusercontent.com/53684676/89902167-1609e480-dc21-11ea-8234-6e485f90d758.png)

<!-- more -->

3. 시스템이 파일 내용을 변경할 수 있도록 권한을 변경해줍니다.

![image-20200811214444183](https://user-images.githubusercontent.com/53684676/89902190-1d30f280-dc21-11ea-8772-af51be64452e.png)

4. `crontab` 수정 명령을 실행합니다.

![image-20200811214547152](https://user-images.githubusercontent.com/53684676/89902215-2326d380-dc21-11ea-8700-ea64685968f0.png)

5. 스케줄을 등록할때 `>>` 다음에 로그 저장 경로를 지정해줍니다. 

   ![image-20200811221435793](https://user-images.githubusercontent.com/53684676/89902234-27eb8780-dc21-11ea-8688-e45fe0fe40d1.png)

- `1` stdout
- `2` stderr
- `>` redirection
- `2>&1` stderr를 stdout으로 리디렉션해서 stdout과 동일하게 처리

### 작업 스케쥴 설정

- `* * * * *` 1분마다 실행
- `30 * * * * ` 매시 30분마다 실행
- `0 0 10 * *` 매월 10일 0시 0분에 실행
- `* * 10 * *` 매월 10일에 1분마다 실행
- `0 0 10 4 *` 매년 4월 10일에 0시 0분에 실행
- `0 0 * * 1` 매주 월요일 0시 0분에 실행
- `0 * * * 1` 매주 월요일 매시 9분에 실행

6. 설정 후 동일하게 esc누르신 후 `:wq` 명령어로 vim에서 나가시면 끝

