FROM node:18 AS builder
COPY . /app
WORKDIR /app
RUN npm install

FROM gcr.io/distroless/nodejs:18
COPY --from=builder /app/index.js /app/index.js
COPY --from=builder /app/public /app/public
COPY --from=builder /app/node_modules /app/node_modules
COPY --from=builder /app/package.json /app/package.json
WORKDIR /app

CMD ["index.js"]
