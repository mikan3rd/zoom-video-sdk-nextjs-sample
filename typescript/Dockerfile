FROM node:18.5-alpine

WORKDIR /app

ARG NEXT_PUBLIC_ZOOM_SDK_KEY
ARG NEXT_PUBLIC_ZOOM_SDK_SECRET

ENV NODE_ENV=production
ENV NEXT_PUBLIC_ZOOM_SDK_KEY=${NEXT_PUBLIC_ZOOM_SDK_KEY}
ENV NEXT_PUBLIC_ZOOM_SDK_SECRET=${NEXT_PUBLIC_ZOOM_SDK_SECRET}

COPY ./typescript ./typescript

WORKDIR /app/typescript

RUN yarn install --production

RUN yarn create-production-env

RUN yarn build

CMD yarn start
