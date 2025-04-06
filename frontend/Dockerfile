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

COPY ./frontend/pnpm-lock.yaml* ./frontend/package.json ./

RUN pnpm install

COPY ./frontend .

EXPOSE 3333

CMD ["pnpm", "dev"]