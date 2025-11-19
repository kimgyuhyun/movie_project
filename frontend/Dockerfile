# 1단계: React 앱 빌드
FROM node:18 AS build
WORKDIR /app

# package.json만 먼저 복사하고 의존성 설치 (캐시 활용)
COPY package*.json ./
RUN npm install

# 소스 코드 복사
COPY . .

# 빌드 실행
RUN npm run build

# 2단계: Nginx로 정적 파일 서빙
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80 