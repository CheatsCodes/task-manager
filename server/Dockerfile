FROM node:18-alpine
WORKDIR /app

COPY package*.json ./
COPY prisma/ ./prisma/
COPY tsconfig.json ./

RUN npm install -g prisma
RUN npx prisma generate
RUN npm ci

COPY src/ ./src/

RUN npm run build

CMD ["node", "dist/index.js"]