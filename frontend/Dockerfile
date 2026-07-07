FROM node:20-alpine
RUN apk add --no-cache libc6-compat
WORKDIR /app

# Install dependencies
COPY package.json package-lock.json ./
RUN npm ci

# Copy source files
COPY . .

# Build the Next.js app
RUN npm run build

# Start the application on port 8080 (Cloud Run default)
ENV PORT 8080
EXPOSE 8080

CMD ["npm", "start"]
