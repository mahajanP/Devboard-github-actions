# Frontend UI
# Created by Prakash Mahajan

# Build stage
FROM dhi.io/node:22-alpine3.24-dev AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install --legacy-peer-deps

COPY . .

# Verify Node and npm are available
RUN node -v && npm -v

# Production stage
FROM dhi.io/node:22-alpine3.24

WORKDIR /app

COPY --from=builder --chown=node:node /app/node_modules ./node_modules
COPY --from=builder --chown=node:node /app/package*.json ./
COPY --from=builder --chown=node:node /app .

# Verify runtime image contains Node.js and npm
RUN node -v && npm -v

USER node

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0", "--port", "5173"]