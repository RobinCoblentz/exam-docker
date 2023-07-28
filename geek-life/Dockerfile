FROM node:20

WORKDIR /graphql-auth
COPY package.json pnpm-lock.yaml ./
RUN npm install -g pnpm && pnpm install
COPY . .
RUN npx prisma generate
CMD npx prisma migrate deploy && pnpm run dev
