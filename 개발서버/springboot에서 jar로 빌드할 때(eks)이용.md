참고 사이트 

https://master.d3s71i2n51x60t.amplifyapp.com/ko/service_launch/flask_backend/

!!CMD 에서 할 일 -- springboot에서 jar로 빌드할 때

#dockerfile 빌드 명령어
docker build -t kyungju620/{demo-oauth:v2} .

#ecr 레포지토리 만드는 명령어
aws ecr create-repository \
--repository-name demo-todo \
--image-scanning-configuration scanOnPush=true \
--region ap-northeast-1

#docker hub에 푸쉬
docker push kyungju620/demo-oauth:v2

!!C9에서 할 일

#docker hub에서 풀
docker pull kyungju620/demo-todo:v1

#aws ecr에 올리기 위한 태그 설정
docker tag kyungju620/demo-todo:v1 680185190569.dkr.ecr.ap-northeast-1.amazonaws.com/demo-todo:latest
#aws ecr에 이미지 푸쉬
docker push 680185190569.dkr.ecr.ap-northeast-1.amazonaws.com/demo-todo:latest 