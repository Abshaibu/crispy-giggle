# Build stage
FROM node:20-alpine AS builder
WORKDIR /app
COPY index.html NiveauGroteskRegular.ttf hero-section.svg ./
RUN ls -la

# Production stage
FROM nginx:alpine
COPY --from=builder /app/index.html /usr/share/nginx/html/
COPY --from=builder /app/NiveauGroteskRegular.ttf /usr/share/nginx/html/
COPY --from=builder /app/hero-section.svg /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]