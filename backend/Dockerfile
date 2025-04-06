FROM node:22.14.0-alpine

RUN apk add --no-cache \
    bash \
    git \
    openssh \
    python3 \
    make \
    g++ \
    && corepack enable \
    && corepack prepare pnpm@latest --activate

WORKDIR /app

COPY ./backend/pnpm-lock.yaml* ./backend/package.json ./

RUN pnpm install

COPY ./backend .

EXPOSE 3333

CMD ["pnpm", "start:dev"]