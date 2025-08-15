# ARG BUILD_FROM
# FROM $BUILD_FROM

FROM node:18-slim

ENV CK_API_ENV=prod

RUN apt-get update && apt-get install -y python3 build-essential

RUN mkdir -p /workspace/node_modules

COPY ["./dist", "./package.json", "/workspace/"]

WORKDIR /workspace

RUN npm install --omit=dev --legacy-peer-deps

EXPOSE 3000

CMD ["node", "main.js"]
