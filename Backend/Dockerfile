##Normal DOckerfile for backend

# FROM node:18
# WORKDIR /app
# COPY package*.json /app
# RUN npm install
# EXPOSE 3001
# COPY . .
# CMD [ "npm" ,"run", "server" ]



##Multi stage Dockerfile for backend

# ---------- Stage 1: Install dependencies ----------

FROM node:18-alpine AS deps
WORKDIR /app
COPY package*.json ./
RUN npm install --only=production


# ---------- Stage 2: Runtime ----------

FROM node:18-alpine
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY . .
EXPOSE 3001
CMD ["node", "index.js"]
