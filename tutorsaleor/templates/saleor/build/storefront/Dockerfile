FROM node:18-alpine

RUN apk add --no-cache git

RUN npm install -g pnpm

WORKDIR /app

RUN git clone -b {{ SALEOR_STOREFRONT_BRANCH }} {{ SALEOR_STOREFRONT_REPOSITORY }} storefront

WORKDIR /app/storefront

# This requires the saleor core service to load the graphql schema
# ENV NEXT_PUBLIC_SALEOR_API_URL="{% if ENABLE_HTTPS %}https{% else %}http{% endif %}://{{ SALEOR_CORE_HOST }}:{{ SALEOR_CORE_PORT }}/graphql/"
# ENV NEXT_PUBLIC_STOREFRONT_URL="{% if ENABLE_HTTPS %}https{% else %}http{% endif %}://{{ SALEOR_STOREFRONT_HOST }}:{{ SALEOR_STOREFRONT_PORT }}/"

# Use default variables
RUN cp .env.example .env

RUN pnpm install

RUN pnpm run build

EXPOSE 3000
