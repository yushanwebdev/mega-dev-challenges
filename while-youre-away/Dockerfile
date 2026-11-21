FROM node:22-alpine
WORKDIR /app
COPY agent.mjs .
ENV DATA_DIR=/data NODE_ENV=production
RUN mkdir /data && chown node:node /data
USER node
CMD ["node", "agent.mjs"]
