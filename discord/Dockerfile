FROM node:22-alpine

RUN apk add --no-cache tzdata dumb-init
ENV TZ=Europe/Paris

WORKDIR /app

COPY package*.json ./
RUN npm ci --omit=dev

COPY . .

ENTRYPOINT ["dumb-init", "--"]
CMD ["node", "index.js"]

STOPSIGNAL SIGTERM
