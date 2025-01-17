# Flask API Server
> 이 레포지토리는 Flask로 구현된 간단한 CRUD 기능을 제공하는 API 서버를 구현했습니다.

## 설정 방법
1. 필요한 패키지 설치
    ```sh
    pip3 install -r requirements.txt
    ```

2. Flask 애플리케이션 실행
    ```sh
    python3 app.py
    ```

<br>

## API 엔드포인트
- `GET /health`: API 서버의 상태 확인
- `POST /records`: 새로운 레코드 생성
- `GET /records`: 레코드 목록 조회
- `GET /records/<id>`: 특정 레코드 조회
- `PUT /records/<id>`: 특정 레코드 수정
- `DELETE /records/<id>`: 특정 레코드 삭제

<br>

## 데이터베이스 설정
- MySQL
- SQLAlchemy

<br>

## Docker 이미지 빌드 및 푸시
1. Docker 이미지 빌드
```sh
docker build -t <dockerhub-username>/my-flask-api:latest .
```
2. Docker Hub에 로그인
```sh
docker login
```
3. Docker 이미지 푸시
```sh
docker push <dockerhub-username>/my-flask-api:latest
````

<br>

## Dockerfile
프로젝트 루트 디렉토리에 Dockerfile을 생성하고 아래 내용을 추가합니다:

```dockerfile
FROM python:3.9-slim

WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
COPY . .

CMD ["python", "app.py"]
```
<br>

## Kubernetes 배포
Docker Hub에 푸시된 이미지를 사용하여 Kubernetes 클러스터에 배포합니다.

해당 내용은 다음 레포지토리를 참고해주세요 !  
[aksProject_infra 링크](https://github.com/aeyong714/aksProject_infra)

<br>
