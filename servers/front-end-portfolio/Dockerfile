FROM node:24-alpine AS base

WORKDIR /app

RUN npm install -g pnpm

COPY ./ /app/

RUN rm -rf node_modules

RUN --mount=type=cache,id=pnpm,target=/pnpm/store pnpm install --frozen-lockfile --prod --filter front-end-portfolio
RUN pnpm front-end-portfolio run build

EXPOSE 3000

CMD ["pnpm", "front-end-portfolio", "run", "start"]
