![header](https://capsule-render.vercel.app/api?type=transparent&fontColor=fa5b6a&text=Harmonica&height=120&fontSize=60&desc=OIDC%202023&descAlignY=85&descAlign=60)

<h4 align='center'><a href="https://github.com/NayeonKeum">금나연</a> <a href="https://github.com/kgw7401">김건우</a> <a href="https://github.com/noooey">박규연</a> <a href="https://github.com/Linho1150">이재준</a></h4>

---
<h1 align='center'>Hybrid 클라우드 사용을 위한 Serverless Switch 플랫폼</h1>

Serverless를 클라우드와 온프레미스 각 환경에 맞게끔 간편하게 변환하여 **Hybrid 인프라 환경**을 더 효율적으로 활용할 수 있게 하는 **Serverless 변환 서비스**를 개발한다.
- OCI Functions, AWS Fargate, GCP Cloud Function과 같은 클라우드 CaaS Serverless와 Knative 기반 온프레미스 Serverless 환경 사이의 양방향 마이그레이션을 지원한다.
- 웹 UI를 제공하여 벤더 간 간편한 스위칭을 할 수 있도록 하고, 변환 과정을 모니터링할 수 있도록 한다.

---
<h2 align='center'>✨기대효과✨</h2>

1. 요구 사항에 따라 클라우드와 온프레미스 환경을 취사 선택하여 Hybrid Serverless 서비스를
운영하는 데 드는 노력을 최소화하고 비용을 절감할 수 있다.
2. 관련 PaaS 솔루션에 Kubernetes 모니터링 및 관리 서비스에 도입하여 기능을 확장시킬 수
있다.
3. 복잡한 CLI나 명령어 없이 웹 UI로 다양한 인프라 사이에서 간편하게 스위칭할 수 있다.

---
<h2 align='center'>개발 환경 구성</h2>
<p align='center'><img src="https://github.com/Harmonica-OIDC2023/.github/assets/68985625/328f89a3-9d03-46dc-80f7-7bb73480bef9"/></p>

---
<h2 align='center'>실행 방법</h2>

### Docker compose로 실행 
[![Docker Hub Logo](https://img.shields.io/badge/DockerHub-Images-yellow.svg?logo=docker)](https://hub.docker.com/repositories/harmonica2023)
```yaml
services:
  web-server:
    image: harmonica2023/web-server:1.1
    platform: linux/amd64
    container_name: web-server
    ports:
      - 8081:3000
    stdin_open: true
    networks:
      - default
  was-server:
    image: harmonica2023/was-server:1.1
    platform: linux/amd64
    container_name: was-server
    ports:
      - 8080:8080
    networks:
      - default
networks:
  default:
    name: harmonica-network
```
---
<h3 align='center'>🚨 Harmonica는 <a href="https://www.oidc.co.kr/">OIDC 2023</a>의 출품작입니다. 대회 기간 동안 무단 도용, 배포 및 상업적 사용을 금지합니다. 🚨</h3>
