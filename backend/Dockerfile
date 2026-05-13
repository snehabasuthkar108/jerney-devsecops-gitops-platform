# ---- Build stage ----
FROM node:20-alpine AS build

WORKDIR /app

COPY package.json package-lock.json* ./

RUN npm ci --only=production && npm cache clean --force

# ---- Production stage ----
FROM node:20-alpine AS production

# Security: Update packages to patch vulnerabilities
RUN apk update && apk upgrade && rm -rf /var/cache/apk/*

# Security: Remove unnecessary package managers
RUN rm -rf /usr/local/lib/node_modules/npm && \
    rm -rf /usr/local/lib/node_modules/yarn && \
    rm -rf /usr/local/lib/node_modules/pnpm

# Security: run as non-root user
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Security: install dumb-init
RUN apk add --no-cache dumb-init=1.2.5-r3

WORKDIR /app

# Copy production dependencies
COPY --from=build /app/node_modules ./node_modules
COPY src/ ./src/

# File ownership
RUN chown -R appuser:appgroup /app

USER appuser

EXPOSE 5000

ENTRYPOINT ["dumb-init", "--"]

CMD ["node", "src/index.js"]
